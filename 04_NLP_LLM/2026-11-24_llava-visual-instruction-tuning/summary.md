# Visual Instruction Tuning (LLaVA)

- **저자 / 연도 / 학회·저널:** Haotian Liu, Chunyuan Li, Qingyang Wu, Yong Jae Lee / 2023 / NeurIPS 2023 (Oral)
- **링크:** [arXiv 2304.08485](https://arxiv.org/abs/2304.08485) · [프로젝트 페이지](https://llava-vl.github.io) · [코드 (GitHub)](https://github.com/haotian-liu/LLaVA)
- **자료 유형:** 논문
- **정리일:** 2026-11-24
- **한 줄 요약:** CLIP 비전 인코더와 LLM(Vicuna)을 **선형 투영층 하나**로 잇고, 이미지를 못 보는 GPT-4로 만든 **멀티모달 지시 데이터 158K**로 튜닝해서, 이미지를 보며 사용자 지시를 따르는 범용 어시스턴트를 만들었다.

> 📌 이 정리를 읽게 된 계기: [2026 성균관대 멀티모달 AI Bias 챌린지](https://github.com/kwjw0815-beep/multimodal-ai-bias-challenge) Step 2(Zero-shot VLM 베이스라인) 전에, VLM이 이미지를 어떻게 "읽는지" 이해하려고 읽었다. 대회에서 쓸 Qwen2.5-VL 같은 최신 VLM도 "비전 인코더 → 연결층 → LLM"이라는 같은 골격을 쓴다.

## TL;DR (3줄)
1. **구조:** 이미지 → CLIP ViT-L/14 → 선형 투영 $\mathbf{W}$ → **시각 토큰(visual tokens)** → Vicuna. 이미지를 LLM의 단어 임베딩 공간으로 옮겨 텍스트 토큰과 나란히 넣는다.
2. **데이터:** 텍스트 전용 GPT-4에게 이미지 대신 **캡션과 바운딩 박스**를 주고, 대화·상세 설명·복잡한 추론 3종의 지시 데이터 158K를 만들었다. 사람이 만든 것은 유형별 시드 예시 몇 개뿐이다.
3. **결과:** 지시 튜닝 전후로 GPT-4 대비 상대 점수가 21.5% → 85.1% (LLaVA-Bench COCO). ScienceQA에서는 단독 90.92%, GPT-4를 심판(judge)으로 쓴 앙상블로 92.53% (당시 SoTA).

---

## 핵심 개념 ①: 이미지가 "단어"가 되는 과정 (직관 → 정의)

**직관:** LLM은 토큰 임베딩의 나열만 읽는다. 그러니 이미지를 **LLM이 읽을 수 있는 임베딩의 나열로 번역**하면 된다. LLaVA는 이 번역기를 행렬 곱 하나로 만들었다.

| 단계 | 형태 | 비유 |
|---|---|---|
| 이미지 $\mathbf{X}_v$ | 픽셀 | 외국어로 쓰인 문서 |
| CLIP 인코더 $g(\cdot)$ | 패치별 특징 벡터 $\mathbf{Z}_v$ | 문서를 읽고 적은 메모 |
| 투영 $\mathbf{W}$ | LLM 임베딩 차원의 벡터 $\mathbf{H}_v$ | 메모를 LLM의 언어로 번역 |
| LLM | 다음 토큰 예측 | 번역문과 질문을 읽고 답을 씀 |

**정의 (식 1):**

$$
\mathbf{H}_v = \mathbf{W} \cdot \mathbf{Z}_v, \qquad \mathbf{Z}_v = g(\mathbf{X}_v)
$$

- $g$는 CLIP ViT-L/14다. 이미지를 14×14 픽셀 패치로 잘라 패치마다 특징을 낸다 (grid features).
- 시각 토큰 수: CLIP ViT-L/14의 기본 입력 224×224라면 $(224/14)^2 = 256$개다 (계산. 논문 본문에는 입력 해상도와 토큰 수가 적혀 있지 않다).
- **마지막 층 직전(penultimate layer)** 의 특징을 쓴다. 저자 가설: 마지막 층은 전역적·추상적 속성에, 직전 층은 국소적 디테일에 더 집중한다 (ScienceQA 90.92% vs 89.96%).
- 더 복잡한 연결 방식(Flamingo의 gated cross-attention, BLIP-2의 Q-Former)도 있다. 하지만 가벼운 선형층을 골라 **데이터 중심 실험을 빨리 반복**할 수 있게 했다.

## 핵심 개념 ②: 2단계 학습

| | Stage 1: 특징 정렬 (Feature Alignment) | Stage 2: 종단 간 미세조정 (End-to-End Fine-tuning) |
|---|---|---|
| 데이터 | CC3M에서 거른 이미지-캡션 595K | LLaVA-Instruct-158K (또는 ScienceQA) |
| 학습하는 것 | 투영 $\mathbf{W}$만 | $\mathbf{W}$ + LLM |
| 고정 (frozen) | 비전 인코더, LLM | 비전 인코더 |
| 의미 | 고정된 LLM에 맞는 **"시각 토크나이저"** 학습 | 지시를 따르는 능력 학습 |
| 비용 (A100 8장) | 1 epoch, 4시간 이내 | 3 epoch, 10시간 이내 |

- 비전 인코더(CLIP)는 **어느 단계에서도 학습되지 않는다.**
- 손실(loss)은 **어시스턴트 답 토큰에만** 건다 (식 3). 이미지와 질문은 조건일 뿐 예측 대상이 아니다.
- 입력 형식 (Table 2): `시스템 메시지 ### Human: 지시 ### Assistant: 답 ### ...`. 첫 턴에서는 이미지를 질문 앞이나 뒤에 무작위로 둔다 (식 2).

## 핵심 개념 ③: 이미지를 못 보는 GPT-4로 이미지 데이터 만들기

- GPT-4(당시 텍스트 전용)에게 이미지를 **기호 표현(symbolic representation)** 으로 바꿔 준다: (i) 장면을 여러 관점에서 묘사한 캡션, (ii) 객체 이름과 바운딩 박스 좌표.
- 유형별 시드 예시 몇 개를 in-context learning 예시로 넣고, COCO 이미지마다 생성한다.
- 결과: 대화 58K + 상세 설명 23K + 복잡한 추론 77K = **158K** (고유 이미지 약 80K). ChatGPT보다 GPT-4가 일관되게 품질이 높았다 (특히 공간 추론).
- ⚠️ 대화 생성 프롬프트(Table 13)에 이런 지시가 있다.

  > *"Only include questions that have definite answers ... Do not ask any question that cannot be answered confidently."*

  "이미지에 없다"고 확실히 말할 수 있는 질문은 넣는다. 하지만 **정보가 부족해서 답할 수 없는 질문은 의도적으로 뺐다.** 모델은 "알 수 없다"가 정답인 예를 거의 보지 못하고 학습한다.

---

## 논문 읽기 질문 (README 기준)

1. **선행 연구:**
   - **NLP의 지시 튜닝(instruction tuning):** InstructGPT/ChatGPT, FLAN-T5/FLAN-PaLM, OPT-IML, Self-Instruct. 기계가 만든 지시 데이터로 오픈소스 LLM을 정렬한 Alpaca, Vicuna, GPT-4-LLM.
   - **멀티모달 모델:** Flamingo(저자 표현으로 "멀티모달의 GPT-3 순간"), BLIP-2, FROMAGe, KOSMOS-1, PaLM-E, OpenFlamingo, LLaMA-Adapter. 이미지-텍스트 쌍으로 학습했지만 **시각-언어 지시 데이터로 튜닝하지는 않았다.**
   - **구성 요소:** 비전 인코더 CLIP (Radford et al., 2021), LLM Vicuna (LLaMA 기반).
   - GPT를 텍스트 주석에 쓰는 연구 (Gilardi et al., 2023: ChatGPT가 크라우드 워커보다 낫다).
2. **연구 동기:**
   - 기존 비전 모델은 과제마다 따로 있고, 언어는 이미지 내용을 **묘사하는 데만** 쓰였다. 사용자 지시에 맞춰 행동을 바꾸는 인터페이스가 없다.
   - LLM은 언어를 "범용 인터페이스"로 쓰는 데 성공했지만 텍스트 전용이다.
   - 핵심 병목은 **시각-언어 지시 데이터가 없다**는 것이다. 사람이 만들기엔 비싸고 정의도 모호하다.
3. **연구 목표:**
   - (i) 이미지-텍스트 쌍을 지시 데이터로 바꾸는 파이프라인 (GPT-4 활용)
   - (ii) CLIP과 Vicuna를 잇는 LMM(Large Multimodal Model) 학습
   - (iii) 멀티모달 지시 따르기 벤치마크 LLaVA-Bench 구축
   - (iv) 데이터·코드·모델 공개
4. **사용 장비/소프트웨어/데이터셋:**
   - 장비: A100 8장. FSDP, gradient checkpointing, BF16·TF32. Adam(weight decay 없음), cosine 학습률, warmup 3%.
   - 하이퍼파라미터: Stage 1은 lr 2e-3, batch 128, 1 epoch. Stage 2는 lr 2e-5, batch 32, 3 epoch. ScienceQA는 12 epoch.
   - 데이터: CC3M 필터링 595K (Stage 1), COCO 기반 LLaVA-Instruct-158K (Stage 2), ScienceQA (객관식 21K, train/val/test = 12,726/4,241/4,241).
   - CC3M 필터링: spaCy로 캡션의 명사구를 뽑아 빈도 3 미만은 버리고, 명사구마다 캡션을 최대 100개까지만 남긴다. 개념 커버리지는 유지하면서 크기를 줄인 것이다.
5. **측정 변수:**
   - **LLaVA-Bench:** GPT-4가 유용성·관련성·정확성·상세함을 보고 1~10점을 매긴다. 정답 묘사(텍스트)를 입력으로 받은 **텍스트 전용 GPT-4 대비 상대 점수(%)** 로 보고한다.
     - COCO: 이미지 30장 × 질문 3종 = 90문항
     - In-the-Wild: 실내·실외 장면, 밈, 그림, 스케치 등 이미지 24장, 60문항
   - **ScienceQA:** 정확도. 과목(자연·사회·언어), 맥락 모달리티(텍스트·이미지·없음), 학년별로 나눈다.
6. **통계 검정 및 결과:**
   - 가설 검정은 없다.
   - In-the-Wild는 추론 3회의 평균 ± 표준편차로 보고한다 (LLaVA 67.3 ± 2.0).
   - 같은 출력을 GPT-4에 3번 채점시켜 채점 자체의 흔들림도 확인했다 (66.7 ± 0.3, 일관됨).
7. **주요 발견:**
   - **지시 튜닝 효과가 압도적이다:** 지시 튜닝 없음 21.5% → 전체 데이터 85.1% (Table 4).
   - **데이터 종류가 서로 돕는다:** 대화 데이터만 쓰면 73.8%다. 상세 설명 5%와 복잡한 추론 10%를 더하면 80.5%로 오르고, 대화 문항 점수까지 오른다 (76.5 → 81.0).
   - **In-the-Wild:** LLaVA 67.3%, BLIP-2 38.1%, OpenFlamingo 19.1%. 복잡한 추론만 보면 81.7%.
   - **ScienceQA:** LLaVA 단독 90.92% (기존 SoTA 91.68%에 근접). GPT-4 2-shot은 82.69%. 두 모델의 답이 다를 때 GPT-4가 다시 판단하는 "GPT-4 as the judge" 앙상블로 **92.53%** (새 SoTA).
   - **실패 사례 "bag of patches":** 냉장고에 요거트와 딸기가 따로 있는데 "딸기 맛 요거트가 있나?"에 "예"라고 답했다. 이미지를 **패치 조각들의 모음**으로 보고 조각 사이의 관계를 놓친 것이다.
   - **설계 ablation (Table 8, ScienceQA):**
     - 직전 층 특징이 마지막 층보다 0.96%p 높다.
     - 추론을 먼저 쓰게(reasoning-first) 하면 수렴은 빠르지만(6 epoch), 최종 성능 차이는 작다.
     - Stage 1(특징 정렬)을 건너뛰면 5.11%p 떨어진다.
     - 7B는 13B보다 1.08%p 낮다.
8. **분야 내 위치:**
   - 지시 튜닝을 시각-언어로 처음 확장한 논문이다.
   - "비전 인코더 + 연결층 + LLM" 골격은 이후 많은 오픈소스 VLM이 따랐다. 후속작 LLaVA-1.5는 연결층을 MLP로 바꿨고, 대회 후보 Qwen2.5-VL도 같은 골격에 동적 해상도를 더했다.
   - GPT-4를 **평가자(LLM-as-a-judge)** 와 **앙상블 심판**으로 쓴 초기 사례다. 저자는 GPT-4를 모델 앙상블에 쓴 것이 처음이라고 밝힌다.
9. **Figure/Table 설명:**
   - **Fig 1:** 구조도. 이미지 → 비전 인코더 → 투영 W → 언어 모델. 언어 지시도 같은 언어 모델로 들어간다.
   - **Table 1·14:** 데이터 생성 예시. 위쪽은 GPT에 준 입력(캡션, 박스), 아래쪽은 3종 응답이다. 이미지 자체는 GPT에 주지 않았다.
   - **Table 2:** 학습 시퀀스 형식. 답 토큰(초록색)에만 손실을 계산한다.
   - **Table 3:** GPT-4 논문의 "차 위에서 다림질하는 남자(Extreme Ironing)" 예시. BLIP-2와 OpenFlamingo는 장면 묘사에 그치고, LLaVA는 "무엇이 이상한가"라는 지시에 맞게 답한다.
   - **Table 4·5:** 학습 데이터 구성별 ablation과 In-the-Wild 비교 (7번 참고).
   - **Table 6:** 어려운 예시 (이치란 라멘, 냉장고). 고해상도 디테일, 넓은 지식, 다국어 이해가 필요하다.
   - **Table 7:** ScienceQA 결과. 이미지 맥락(IMG) 문항에서도 텍스트 전용 GPT-4 심판이 성능을 올렸다. **이미지가 없어도 풀리는 문항**이 섞여 있기 때문이다.
   - **Table 8:** 설계 선택 ablation (7번 참고).
   - **Table 10 (부록):** 심판 예시. LLaVA는 흔들의자의 등받이와 좌석이 "비단"이라고 잘못 보고 B를 골랐다. 텍스트 전용 GPT-4는 "흔들의자는 보통 나무"라는 상식으로 A를 골랐다. 심판은 두 답의 근거가 얼마나 그럴듯한지 비교해 A를 택했다.
   - **Fig 6 (부록):** 학습 데이터에 한 번도 나오지 않은 일론 머스크를 알아본다. CLIP 사전학습에서 본 것이 LLM까지 전달된다는 뜻이다.
   - **Fig 7 (부록):** CC3M 필터링 전후 명사구 통계.
10. **재현성:**
    - 코드, 생성 데이터(LLaVA-Instruct-158K), 벤치마크, 체크포인트가 공개되어 있다 ([GitHub](https://github.com/haotian-liu/LLaVA)). 데이터 생성 프롬프트와 few-shot 예시도 부록 F와 코드베이스에 있다.
    - 다만 데이터 생성과 평가가 **GPT-4 API**에 의존한다. API 모델은 시간이 지나며 바뀌므로 같은 데이터와 점수를 다시 만들기는 어렵다 (추측).
    - 학습 비용은 A100 8장 기준 Stage 1 4시간, Stage 2 10시간으로 대형 모델치고 가볍다.
11. **저자, 연도, 제목:** Liu, Li, Wu, Lee, 2023, *Visual Instruction Tuning* (NeurIPS 2023 Oral)
12. **저자 배경:**
    - 소속: Haotian Liu·Yong Jae Lee (University of Wisconsin–Madison), Chunyuan Li (Microsoft Research), Qingyang Wu (Columbia University).
    - 참고문헌을 보면 Chunyuan Li는 언어로 보강한 비전 모델 연구(GLIP, ELEVATER 벤치마크, 멀티모달 파운데이션 모델 서베이)에 참여해 왔다.
    - 같은 팀이 후속작 LLaVA-1.5 (CVPR 2024)를 냈다.
13. **모르는 용어/개념:**
    - **Instruction tuning (지시 튜닝):** "지시문 → 바람직한 응답" 쌍으로 LLM을 미세조정해, 처음 보는 과제의 지시도 따르게 만드는 것.
    - **LMM (Large Multimodal Model):** 이미지 등 여러 모달리티를 입력받는 대규모 모델. VLM(Vision-Language Model)과 거의 같은 뜻으로 쓰인다.
    - **CLIP:** 인터넷의 이미지-텍스트 쌍 4억 개로 대조 학습(contrastive learning)을 한 모델. 짝이 맞는 이미지와 텍스트의 임베딩을 가깝게 만든다.
    - **ViT-L/14:** Large 크기의 Vision Transformer. 이미지를 14×14 픽셀 패치로 잘라 토큰처럼 다룬다.
    - **Grid features:** 패치별 특징 벡터의 격자. 이미지 전체를 요약한 벡터 하나 대신 패치 전부를 쓴다.
    - **Projection (투영):** 한 벡터 공간을 다른 공간으로 옮기는 변환. 여기서는 행렬 곱 하나다.
    - **Feature alignment (특징 정렬):** 시각 특징이 LLM의 단어 임베딩과 같은 의미 공간에 놓이도록 맞추는 것.
    - **Auto-regressive objective:** 앞 토큰들로 다음 토큰을 예측하는 학습 목표.
    - **In-context learning / few-shot:** 가중치를 바꾸지 않고 프롬프트에 예시 몇 개를 넣어 과제를 수행시키는 것.
    - **Chain-of-thought (CoT):** 답보다 추론 과정을 먼저 생성하게 하는 것.
    - **FSDP / gradient checkpointing / BF16:** 큰 모델 학습에서 GPU 메모리를 아끼는 기법. 각각 파라미터를 여러 GPU에 나눠 두기, 중간값을 저장하지 않고 다시 계산하기, 16비트 부동소수점 쓰기다.
    - **Hallucination (환각):** 입력에 근거하지 않은 내용을 생성하는 것.
14. **나의 생각:**
    - **구조보다 데이터가 행동을 정한다.** 선형층 하나로 충분했다는 것은 "LLM이 이미 지식을 갖고 있고, 시각 정보는 그 공간으로 옮기기만 하면 된다"는 뜻이다. 실제로 지시 튜닝 유무가 21.5%와 85.1%를 갈랐다.
    - **평가의 한계:** LLaVA-Bench는 GPT-4가 채점하고, In-the-Wild는 60문항뿐이다. 기준이 텍스트 전용 GPT-4라서 100%가 사람 수준을 뜻하지도 않는다.
    - **"확실한 질문만" 데이터와 유보 능력의 공백 (추측):** 학습 데이터에 답할 수 없는 질문이 없으면, 모델은 정보가 부족해도 일단 답하는 쪽으로 기울 수 있다. BBQ의 ambiguous 문항에서 섣불리 고르는 실패와 연결된다. 한편 후속작 LLaVA-1.5에서 지시 한 문장으로 유보가 크게 늘어난 것(아래 절)을 보면, 유보는 **지시로 끌어낼 수 있는 행동**이기도 하다.
    - **"상식" 심판은 양날의 검 (추측):** ScienceQA에서 텍스트 전용 GPT-4 심판이 이긴 근거는 "흔들의자는 보통 나무"라는 **사전 지식(prior)** 이었다. 그런데 편향 문제에서는 "보통 그렇다"가 바로 **고정관념**이다. 같은 앙상블을 편향 과제에 그대로 쓰면 오히려 편향을 키울 수 있다.
    - **편향은 두 경로로 들어온다:** 저자도 부록 A에 *"Bias can be transferred from the base models to LLaVA, both from the vision encoder (CLIP) and the language decoder (LLaMA/Vicuna)."* 라고 썼다. 그런데 비전 인코더는 끝까지 고정이고, 지시 데이터도 사람이 쓴 COCO 캡션에서 만들어졌다. 캡션에 담긴 고정관념이 그대로 옮겨 갈 수 있다 (추측).
    - **"bag of patches"와 거짓 근거 (추측):** 한 이미지에 인물과 물건이 같이 있으면, 실제로는 관계가 없어도 "그 사람의 물건"처럼 관계를 지어낼 수 있다. 근거처럼 보이지만 근거가 아닌 시각 단서다.

---

## 후속작 LLaVA-1.5에서 확인한 것 (대회와 직접 관련)

> 출처: Liu et al., *Improved Baselines with Visual Instruction Tuning*, CVPR 2024 ([arXiv 2310.03744](https://arxiv.org/abs/2310.03744)). 논문 전체를 정리하지 않고, 대회에 필요한 부분만 원문에서 확인했다.

| 항목 | LLaVA | LLaVA-1.5 |
|---|---|---|
| 비전 인코더 | CLIP ViT-L/14 | CLIP ViT-L/14 **336px** (시각 토큰 576개, 계산) |
| 연결층 | 선형 투영 | **2층 MLP** |
| LLM | Vicuna | Vicuna v1.5 |
| 지시 데이터 | LLaVA-Instruct-158K | + 학술 VQA 데이터(VQAv2, GQA, A-OKVQA 등)와 **응답 형식 프롬프트** |
| 학습 시간 (A100 8장) | 4시간 + 10시간 | 약 6시간 + 20시간 |

**응답 형식 프롬프트 (response formatting prompt):** 질문 끝에 출력 형식을 정하는 한 문장을 붙인다.

| 용도 | 프롬프트 |
|---|---|
| 객관식 (학습: A-OKVQA / 평가: ScienceQA, MMBench, SEED-Bench) | *"Answer with the option's letter from the given choices directly."* |
| 단답형 (VQAv2, GQA 등) | *"Answer the question using a single word or phrase."* |
| 답할 수 없는 질문 포함 (VizWiz, 평가에만 사용) | *"When the provided information is insufficient, respond with 'Unanswerable'. Answer the question using a single word or phrase."* |

- VizWiz용 지시는 **학습 때 보지 못한 형식**인데도 모델이 따랐다. 답할 수 없는 질문에서의 점수가 11.1% → **67.8%** 로 올랐다.
- 입력 해상도를 448²로 올리면 환각이 크게 줄었다. 저자 해석: 학습 데이터의 디테일이 해상도 부족으로 보이지 않으면, 모델은 "지어내기"를 배운다.

---

## 데이터사이언티스트 관점 Takeaway
- **실무 적용 포인트:**
  - **강한 모델로 데이터 형식 바꾸기:** 이미지를 못 보는 GPT-4에 캡션과 박스를 줘서 이미지 지시 데이터를 만든 것처럼, 가진 메타데이터를 강한 LLM으로 학습 데이터 형식으로 바꾸는 것은 합성 데이터(synthetic data)의 범용 패턴이다. 단, 생성 프롬프트의 규칙("확실한 질문만")이 모델 행동에 그대로 새겨진다.
  - **단순한 베이스라인부터:** 선형층을 고른 이유가 "데이터 중심 실험을 빨리 반복하기 위해서"였다.
  - **Ablation 표가 설계 근거다:** Table 4·8처럼 하나씩 빼 보며 기여도를 잰다.
  - **LLM-as-a-judge를 쓸 때:** 채점을 반복해 일관성을 확인하되, 기준 모델과 소규모 벤치마크라는 한계를 함께 보고한다.
- **면접/포트폴리오에 쓸 수 있는 포인트:**
  - "VLM은 이미지를 어떻게 LLM에 넣나?" → 비전 인코더 → 투영 → 시각 토큰 → LLM, 그리고 2단계 학습(정렬 → 지시 튜닝)으로 설명할 수 있다.
  - "왜 비전 인코더를 고정하나?" → 논문은 이유를 따로 밝히지 않는다. 사전학습된 시각 표현을 보존하고 학습 비용을 줄이려는 것으로 보인다 (추측).
  - 챌린지와 연결: "학습 데이터 설계가 모델의 유보 행동을 만든다"는 가설을 세우고, 응답 형식 프롬프트로 검증한 경험으로 이어 갈 수 있다.
