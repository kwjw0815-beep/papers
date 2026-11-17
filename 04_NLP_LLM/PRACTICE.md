# 실습 가이드 — NLP LLM

[필독 목록](READING_LIST.md)의 자료를 **읽고 → 해 보고 → 기억하는** 순서로 쓰는 문서. 읽는 요령은 [논문 읽기 워크북](../00_Foundations/10_paper-reading-workbook.md), 노트북 실행법은 [LABS.md](../LABS.md).

## 이 폴더의 실습
- [lab01_tokenizer_attention_from_scratch](labs/lab01_tokenizer_attention_from_scratch.ipynb) — BPE·어텐션 직접 구현
- [lab02_embeddings_retrieval_rag](labs/lab02_embeddings_retrieval_rag.ipynb) — 검색·RAG·오류 분석
- [lab03_llm_eval_error_bars](labs/lab03_llm_eval_error_bars.ipynb) — 평가 통계·편향 점수 신뢰구간
- 모델을 직접 학습·해부하는 실습은 [12_Open_Models](../12_Open_Models)

## 자료 유형별 기본 과제
| 유형 | 할 일 | 남기는 것 |
|---|---|---|
| 논문 | 1차 읽기(10분) → 주장-증거 표 → 14개 질문 노트 | `summary.md` + 기억 점검 질문 3개 |
| 영상·강의 | 보기 전에 "알고 싶은 것 3개"를 적고, 본 뒤 답을 쓴다. 코드가 나오면 따라 치지 말고 **멈춘 뒤 먼저 써 본다** | 미디어 노트(`summary_media.md`) |
| 책·문서 | 한 장을 읽고 책을 덮은 채 핵심 3줄을 쓴다. 연습문제·예제 코드를 하나 이상 실행 | 장별 3줄 요약 |
| 블로그·뉴스 | 주장 1개와 근거 1개를 뽑고, 근거의 출처(원 논문·데이터)를 따라가 본다 | 한 줄 메모 + 원출처 링크 |
| 도구·저장소 | 공식 예제 하나를 실행하고, 내 데이터(또는 실습 노트북의 데이터)에 적용 | 실행한 코드 조각 |

## ★ 코어 자료 가이드
### Attention Is All You Need
[arXiv 1706.03762](https://arxiv.org/abs/1706.03762)

- **이 논문이 답하는 질문:** 순환·합성곱 없이 어텐션만으로 시퀀스를 더 잘, 더 싸게 변환할 수 있는가.
- **읽기 가이드:** 먼저 [Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/). 논문은 Figure 1(구조) → 3.2절(어텐션 식) → 3.5절(위치 인코딩) → 4절의 복잡도 표 → 결과 표 → 모델 변형 표(ablation) 순. **주장-증거 표 풀이:** (1) 품질: WMT14 영→독 28.4 BLEU, 영→불 41.8 BLEU — 결과 표. (2) 비용: 영→불 모델을 GPU 8개로 3.5일 — 결과 표의 학습 비용 열. (3) 구성요소의 필요성: 헤드 수·차원·위치 인코딩 방식을 바꾼 변형 표.
- **실습:** Lab 01 전체. 그다음 [tiny GPT 학습](../12_Open_Models/labs/lab02_train_tiny_gpt_end_to_end.ipynb).

**기억 점검**
1. Q, K, V의 역할은?
2. √d_k로 나누는 이유는?
3. self-attention의 층당 계산 복잡도는?

<details><summary>답 확인</summary>

1. Query: 찾는 것, Key: 각 위치의 색인, Value: 실제로 전달되는 내용. QKᵀ로 관련도를 구해 V를 가중 평균한다.
2. 차원이 크면 내적이 커져 softmax가 포화되고 기울기가 작아지기 때문.
3. 시퀀스 길이 n에 대해 O(n²·d).
</details>

### BERT
[arXiv 1810.04805](https://arxiv.org/abs/1810.04805)

- **이 논문이 답하는 질문:** 라벨 없는 텍스트로 양방향 문맥 표현을 사전학습해 여러 과제에 미세조정할 수 있는가.
- **읽기 가이드:** 입력 표현 그림 → 사전학습 과제 두 개(MLM, NSP) → 미세조정 그림 → ablation(양방향의 효과, NSP의 효과). GLUE 표에서는 비교 대상(GPT, ELMo)과 무엇이 다른지를 본다.
- **실습:** Hugging Face의 `fill-mask` 파이프라인으로 가린 단어를 맞혀 보고, 같은 문장을 GPT류 모델(다음 토큰 예측)과 비교한다.

**기억 점검**
1. MLM이란? 왜 필요한가?
2. BERT로 텍스트 생성이 어려운 이유는?

<details><summary>답 확인</summary>

1. 입력 토큰 일부를 가리고 맞히는 과제. 양방향 문맥을 쓰면서도 '답을 미리 보는' 문제를 피하기 위해.
2. 왼쪽에서 오른쪽으로 다음 토큰을 예측하도록 학습되지 않았다(인코더).
</details>

### Retrieval-Augmented Generation (RAG)
[arXiv 2005.11401](https://arxiv.org/abs/2005.11401)

- **이 논문이 답하는 질문:** 모델 가중치에 없는(또는 낡은) 지식을, 검색한 문서로 보완해 생성할 수 있는가.
- **읽기 가이드:** 구조 그림에서 retriever와 generator가 각각 무엇인지, 무엇이 함께 학습되는지 확인. 요즘의 RAG(학습 없이 프롬프트에 붙이기)와 무엇이 다른지 적는다.
- **실습:** Lab 02 전체. 특히 5절(검색 오류와 생성 오류를 따로 채점).

**기억 점검**
1. RAG의 세 단계는?
2. RAG가 틀렸을 때 가장 먼저 구분할 것은?

<details><summary>답 확인</summary>

1. 검색 → 프롬프트 보강 → 생성.
2. 정답 문서를 검색하지 못한 것인지, 검색은 됐는데 생성이 틀린 것인지.
</details>

### Adding Error Bars to Evals
[arXiv 2411.00640](https://arxiv.org/abs/2411.00640)

- **이 논문이 답하는 질문:** LLM 평가 점수의 차이가 진짜인지 우연인지 어떻게 판단하는가.
- **읽기 가이드:** 서론의 권고 5개를 먼저 적고, 각 권고가 본문의 어느 식에 해당하는지 연결한다. 실험 결과가 없는 방법론 논문이다.
- **실습:** Lab 03 전체.

**기억 점검**
1. 권고 다섯 가지는?
2. 문항 400개, 정확도 80%의 95% 신뢰구간은?

<details><summary>답 확인</summary>

1. CLT로 표준오차 계산, 문항이 묶음이면 군집 표준오차, 답 재추출·다음 토큰 확률로 분산 축소, 두 모델은 짝지은 차이로 비교, 검정력 분석.
2. 표준오차 0.02 → 80% ± 3.9%p.
</details>

### BBQ: A Hand-Built Bias Benchmark for QA
[arXiv 2110.08193](https://arxiv.org/abs/2110.08193)

- **이 논문이 답하는 질문:** QA 모델이 사회적 고정관념에 따라 답하는 정도를 어떻게 잴 것인가.
- **읽기 가이드:** 이미 정리한 [노트](2026-11-03_bbq-bias-benchmark-qa/summary.md)를 워크북 7절의 채점표로 채점해 본다.
- **실습:** Lab 03의 5절(편향 점수에 템플릿 단위 신뢰구간 붙이기).

**기억 점검**
1. 모호한 문맥과 명확한 문맥의 정답은 각각?
2. s_AMB에 (1 − 정확도)를 곱하는 이유는?

<details><summary>답 확인</summary>

1. 모호한 문맥은 항상 UNKNOWN, 명확한 문맥은 문맥이 지목한 사람.
2. 정답(UNKNOWN)을 많이 맞힐수록 치우침의 영향이 작다는 것을 반영하기 위해.
</details>


## 그 밖의 자료
코어가 아닌 자료는 위의 "자료 유형별 기본 과제"를 따른다. 특정 자료의 읽기 가이드나 퀴즈가 필요하면 Claude에게 "○○ 실습 가이드 만들어줘"라고 요청하면 이 문서에 추가된다.
