# 모델별 가이드

모델마다 **무엇이 공개됐는지, 어디서 받는지, 무엇을 볼지, 무엇을 해 볼지**를 정리했다.
사실 관계는 2026-11에 각 모델의 공식 저장소·모델 카드·논문에서 확인했다. 공개 범위는 바뀔 수 있으니 공부를 시작할 때 [체크리스트](01_openness-levels.md#4-판별-체크리스트-모델-하나에-10분)로 다시 확인한다.

| 순서 | 모델 | 한 줄 요약 | 필요한 장비 |
|---|---|---|---|
| 1 | [직접 학습 + nanoGPT](#1-직접-학습--nanogpt) | 가장 작은 규모로 전 과정을 완주 | CPU |
| 2 | [TinyStories](#2-tinystories) | 작은 모델이 무엇을 배울 수 있는지 | CPU |
| 3 | [Pythia](#3-pythia) | 학습 과정을 체크포인트로 관찰 | CPU |
| 4 | [SmolLM2 / SmolLM3](#4-smollm2--smollm3) | 현대적 소형 모델의 데이터·학습 단계 | CPU ~ GPU |
| 5 | [nanochat](#5-nanochat) | 토크나이저부터 채팅 UI까지 한 저장소 | CPU(축소) ~ GPU 노드 |
| 6 | [OLMo 2 / Olmo 3](#6-olmo-2--olmo-3) | 대규모 모델의 전 과정 문서와 단계별 체크포인트 | 읽기 + (1B는 CPU 추론) |
| 7 | [Apertus](#7-apertus) | 데이터 규정 준수와 다국어 | 읽기 중심 |
| 8 | [Marin](#8-marin) | 실패까지 기록하는 공개 연구 | 읽기 |
| 9 | [KORMo](#9-kormo) | 한국어로 학습한 완전 공개 모델 | 읽기 + 무료 Colab(미세조정) |
| - | [비교군: 가중치 공개 모델](#비교군-가중치만-공개된-모델) | Llama, Gemma, Qwen, DeepSeek, gpt-oss, 한국어 모델 | - |
| - | [다른 분야의 공개 모델](#다른-분야의-공개-모델) | 시계열, 비전-언어, 정형 데이터 | - |

---

## 1. 직접 학습 + nanoGPT

**무엇인가.** 가장 완전한 공개 모델은 내가 학습한 모델이다. [lab02](labs/lab02_train_tiny_gpt_end_to_end.ipynb)에서 한 번 완주한 뒤, 같은 일을 하는 표준 코드인 [nanoGPT](https://github.com/karpathy/nanoGPT)(MIT)를 읽는다.

**공개된 것.** 코드 전부(모델 약 300줄, 학습 루프 약 300줄), 데이터 준비 스크립트, 설정 파일. 가중치는 내가 만든다.

**저장소 README에서 확인한 사실**
- 셰익스피어 글자 단위 모델: 문맥 256자, 폭 384, 6층, 6헤드. A100 한 장에서 약 3분.
- CPU용 명령이 README에 있다(4층, 폭 128, 문맥 64로 줄인 설정, 약 3분).
- GPT-2(124M) 재현: OpenWebText로 여러 GPU에서 약 4일, 검증 손실 약 2.85. 비교용으로 OpenAI의 GPT-2 124M 체크포인트는 같은 데이터에서 검증 손실 3.12.

**무엇을 볼 것인가**
| 파일 | 볼 것 |
|---|---|
| `model.py` | `CausalSelfAttention`, `MLP`, `Block`, `GPT` 네 클래스. lab02의 내 코드와 한 줄씩 대응시킨다 |
| `train.py` | `get_lr`(warmup + 코사인), 기울기 누적, `estimate_loss`, 체크포인트 저장 |
| `config/` | 실험 하나 = 설정 파일 하나라는 관리 방식 |
| `sample.py` | 저장된 체크포인트에서 생성 |

**해 볼 것**
1. CPU 명령으로 셰익스피어 모델을 학습하고 `sample.py`로 생성한다.
2. 한 번에 하나만 바꿔 다시 학습한다: 층 수, 폭, 문맥 길이, dropout, 학습률. "바꾼 것 → 예측 → 검증 손실 → 해석"을 표로 남긴다.
3. Karpathy의 영상 *[Let's build GPT](https://www.youtube.com/watch?v=kCc8FmEb1nY)*, *[Let's reproduce GPT-2 (124M)](https://www.youtube.com/watch?v=l8pRSuU81PU)* 를 코드와 함께 본다.
4. 같은 내용을 책으로: Raschka, [*Build a Large Language Model (From Scratch)*](https://github.com/rasbt/LLMs-from-scratch) — 장별 노트북, OpenAI 가중치 불러오기, 미세조정까지.

---

## 2. TinyStories

**무엇인가.** 3~4세 아이가 아는 단어만으로 쓴 짧은 이야기 데이터셋(GPT-3.5·GPT-4로 생성)과, 그것으로 학습한 아주 작은 모델들. 논문의 주장은 "총 1천만 파라미터 미만이거나 Transformer 블록이 하나뿐인 모델도, 이 데이터에서는 문법이 맞고 일관된 여러 문단의 이야기를 쓴다"는 것이다. → [논문](https://arxiv.org/abs/2305.07759)

**공개된 것.** 데이터([roneneldan/TinyStories](https://huggingface.co/datasets/roneneldan/TinyStories), CDLA-Sharing-1.0), 모델 가중치(1M·3M·8M·28M·33M 등). 데이터 카드에 평가 프롬프트 파일도 있다.

**무엇을 볼 것인가**
- 데이터 뷰어에서 이야기 20개를 읽는다. 어휘와 문장 구조가 얼마나 제한되어 있는가?
- 논문의 평가 방식: 정답이 없는 "이야기 품질"을 어떻게 쟀는가(다른 LLM에게 문법·창의성·일관성을 채점시킴). 이 평가의 약점은?

**해 볼 것**
1. 33M 모델과 1M 모델에 같은 이야기 시작 문장을 주고 이어 쓰게 한다. 무엇이 다른가?
2. lab02의 학습 데이터를 TinyStories 일부로 바꿔 학습한다. 글자 모델 대신 BPE 토큰을 쓰면 어떻게 달라지나?
3. 왜 큰 웹 말뭉치로는 작은 모델이 일관된 글을 못 쓰는데 이 데이터로는 되는가? 논문의 설명을 내 말로 정리한다.

---

## 3. Pythia

**무엇인가.** 학습 과정 자체를 연구하도록 만든 모델 묶음(EleutherAI). → [논문](https://arxiv.org/abs/2304.01373) · [저장소](https://github.com/EleutherAI/pythia)

**공개된 것** (저장소 README·논문 초록)
- 8개 크기(70M, 160M, 410M, 1B, 1.4B, 2.8B, 6.9B, 12B) × 2종(the Pile / 중복 제거한 the Pile) = 16개 모델
- 모든 모델이 **같은 데이터를 같은 순서로** 학습(각 약 3,000억 토큰)
- 모델마다 체크포인트 **154개**: step 0(초기화), 1, 2, 4, 8, …, 512, 1000, 그 뒤 1,000 스텝마다
- 토큰화된 데이터, 데이터 로더 재구성 스크립트, 학습 코드, 학습 로그
- 라이선스 Apache-2.0

| 크기 | 층 수 | 폭 | 헤드 수 | 학습률 |
|---|---|---|---|---|
| 70M | 6 | 512 | 8 | 1.0e-3 |
| 160M | 12 | 768 | 12 | 6.0e-4 |
| 410M | 24 | 1024 | 16 | 3.0e-4 |
| 1B | 16 | 2048 | 8 | 3.0e-4 |

(전체 표는 저장소 README. 배치 크기는 모두 2M 토큰.)

**불러오는 법** (README의 예)
```python
from transformers import GPTNeoXForCausalLM, AutoTokenizer
model = GPTNeoXForCausalLM.from_pretrained("EleutherAI/pythia-70m-deduped", revision="step3000")
tokenizer = AutoTokenizer.from_pretrained("EleutherAI/pythia-70m-deduped", revision="step3000")
```

**무엇을 볼 것인가**
- 같은 문장에 대한 손실이 step에 따라 어떻게 내려가는가 (노트북 없음 — 아래 절차대로 직접 작성)
- 크기가 다른 모델이 **같은 step에서** 얼마나 다른가(같은 데이터를 봤으므로 공정한 비교)
- 논문의 사례 연구: 암기, 단어 빈도와 few-shot 성능, 성별 편향 줄이기. 각 사례가 "체크포인트와 데이터 순서가 공개되어 있어서" 가능했던 이유

**해 볼 것**
1. 체크포인트 6~8개에서 같은 프롬프트의 이어 쓰기를 비교해 표로 만든다.
2. "철자 → 문법 → 사실"의 순서로 배운다는 가설을 세우고, 각각을 재는 문장 세트를 만들어 확인한다.
3. 논문 주의 사항 읽기: README에 6.9B와 12B는 설정 누락으로 초기화가 달랐다는 기록이 있다. 공개 프로젝트가 **실수를 어떻게 기록하는지** 본다.

---

## 4. SmolLM2 / SmolLM3

**무엇인가.** Hugging Face의 소형 모델 계열. 작은 모델을 잘 만들려면 **데이터를 어떻게 구성해야 하는가**에 초점이 있다.

**SmolLM2** (135M · 360M · 1.7B) → [논문](https://arxiv.org/abs/2502.02737)
- 논문 초록: 1.7B 모델을 약 11조 토큰으로 여러 단계에 걸쳐 학습. 웹 텍스트에 수학·코드·지시 따르기 데이터를 섞음. 부족한 단계를 위해 FineMath, Stack-Edu, SmolTalk 데이터셋을 새로 만듦. 모델과 데이터셋 공개.
- 중간 체크포인트 저장소가 따로 있다(`SmolLM2-135M-intermediate-checkpoints` 등).
- 135M 모델은 CPU에서 바로 돌아간다 → [lab01](labs/lab01_inspect_open_model.ipynb)의 대상.

**SmolLM3** (3B) → [모델 카드](https://huggingface.co/HuggingFaceTB/SmolLM3-3B)
- 카드의 설명: "가중치 + 공개 데이터 혼합과 학습 설정을 포함한 전체 학습 세부 사항"을 공개한 fully open 모델.
- 구조: GQA와 NoPE(3:1)를 쓰는 디코더 전용 Transformer. 11.2조 토큰으로 사전학습(웹·코드·수학·추론 데이터의 단계별 커리큘럼).
- 후처리: 추론 데이터 1,400억 토큰으로 중간학습 → SFT → APO(선호 학습의 한 종류).
- 6개 언어, 추론 모드 켜기/끄기, 64k 문맥(YaRN으로 128k까지).
- 공개 자원: 사전학습 데이터 모음, 학습·평가 설정과 코드([huggingface/smollm](https://github.com/huggingface/smollm)), 중간 체크포인트([SmolLM3-3B-checkpoints](https://huggingface.co/HuggingFaceTB/SmolLM3-3B-checkpoints)). 카드 작성 시점에 중간학습·후처리 데이터는 "나중에 올릴 예정"이라고 적혀 있다 → 지금 올라와 있는지 직접 확인해 볼 것.
- 학습 장비·도구도 적혀 있다: H100 384개, 학습 프레임워크 nanotron, 데이터 처리 datatrove, 평가 lighteval.

**무엇을 볼 것인가**
- SmolLM2 논문의 **데이터 ablation**: 어떤 데이터 조합이 어떤 능력을 올렸나. "모델 구조는 그대로 두고 데이터만 바꾸는" 연구의 예.
- SmolLM3 모델 카드를 **좋은 모델 카드의 본보기**로 읽는다. 평가 표 아래의 조건 설명(zero-shot 여부 등)까지.

**해 볼 것**
1. [lab01](labs/lab01_inspect_open_model.ipynb)을 SmolLM2-135M로 끝낸 뒤, 360M으로 바꿔 파라미터 구성 비율이 어떻게 달라지는지 본다.
2. base 모델과 instruct 모델에 같은 질문을 넣어 출력 차이를 본다.
3. [nanowhale](https://huggingface.co/HuggingFaceTB/nanowhale-100m) (2026): 대형 공개 가중치 모델(DeepSeek-V4)의 구조를 약 1.1억 파라미터로 줄여 **처음부터** 학습한 교육용 모델. 모델 카드의 구조 표와 [학습 코드](https://github.com/huggingface/nanowhale)를 본다. "가중치만 공개된 큰 모델의 구조를, 작은 완전 공개 모델로 공부하는" 방법의 예다.

---

## 5. nanochat

**무엇인가.** 한 저장소 안에서 토크나이저 학습 → 사전학습 → SFT → RL → 평가 → 채팅까지 하는 최소한의 LLM 학습 코드(Karpathy, MIT). → [저장소](https://github.com/karpathy/nanochat)

**저장소 README(2026)에서 확인한 사실**
- "GPU 노드 하나에서 돌도록 설계", "코드가 작고 고치기 쉬움", "토큰화·사전학습·미세조정·평가·추론의 주요 단계를 모두 포함".
- GPT-2 수준의 모델을 8×H100 노드에서 약 2시간(약 48달러)에 학습할 수 있다고 소개한다. 2019년 GPT-2의 학습 비용은 약 4만 3천 달러였다고 비교한다.
- **Time-to-GPT-2 리더보드**: GPT-2(1.6B)의 CORE 점수를 넘는 데 걸리는 시간을 재는 기록표. 2026년 1~3월에 3.04시간 → 1.65시간으로 줄어든 과정이 변경 내용과 함께 적혀 있다(데이터셋 교체, 배치 크기 조정, AI 에이전트를 이용한 자동 실험 등).
- 깊이(`--depth`) 하나로 폭·헤드 수·학습률 등이 정해지도록 만들어져 있다.
- CPU·Apple Silicon용 축소 예제: `runs/runcpu.sh`.
- 예시 가중치: [karpathy/nanochat-d32](https://huggingface.co/karpathy/nanochat-d32) 등.

**무엇을 볼 것인가** (README의 파일 구조)
| 경로 | 내용 |
|---|---|
| `runs/speedrun.sh` | 전 과정을 순서대로 실행하는 스크립트 — **목차처럼 읽는다** |
| `scripts/tok_train.py`, `tok_eval.py` | 토크나이저 학습과 압축률 평가 |
| `scripts/base_train.py`, `base_eval.py` | 사전학습, CORE 점수·bits per byte 평가 |
| `scripts/chat_sft.py`, `chat_rl.py`, `chat_eval.py` | 대화 형식 미세조정, 강화학습, 채팅 과제 평가 |
| `nanochat/gpt.py`, `optim.py`, `engine.py` | 모델, 옵티마이저(AdamW + Muon), KV 캐시 추론 엔진 |
| `tasks/` | 평가·학습 과제 정의(ARC, GSM8K, HumanEval, MMLU, SmolTalk) |

**해 볼 것**
1. `runs/speedrun.sh`를 실행하지 말고 **읽으면서**, 각 줄이 [03_training-pipeline.md](03_training-pipeline.md)의 어느 단계인지 주석을 단다.
2. `runs/runcpu.sh`로 축소판을 돌린다.
3. README의 리더보드에서 기록이 갱신된 커밋 하나를 골라 무엇을 바꿨는지 읽는다.
4. (선택, 유료) GPU 노드를 빌려 speedrun을 완주하고 내 모델과 대화한다.
5. [autoresearch](https://github.com/karpathy/autoresearch) (2026): AI 에이전트가 학습 코드를 고치고 5분짜리 실험을 반복하도록 만든 저장소. 학습 코드 전체가 공개되어 있어야 가능한 연구 방식의 예로 README만 읽어 본다.

---

## 6. OLMo 2 / Olmo 3

**무엇인가.** Ai2(Allen Institute for AI)의 완전 공개 언어모델 계열. 규모가 크면서(1B~32B) 데이터·코드·가중치·체크포인트를 함께 낸다.

**OLMo 2** → [논문](https://arxiv.org/abs/2501.00656)
- 논문 초록: 가중치, 전체 학습 데이터, 학습 코드와 레시피, 학습 로그, 수천 개의 중간 체크포인트를 공개. 학습 안정성 개선과 후반부 특화 데이터(Dolmino Mix) 커리큘럼을 설명.
- [OLMo 2 1B 모델 카드](https://huggingface.co/allenai/OLMo-2-0425-1B): 16층, 폭 2048, 16헤드, 문맥 4,096, 학습 토큰 약 4조. 단계별 모델(Base → SFT → DPO → Instruct)이 각각 올라와 있다.
- 1B는 CPU에서도 추론할 수 있는 크기라, "큰 프로젝트의 가장 작은 모델"로 실습하기 좋다.

**Olmo 3** (2025-11, 이후 3.1) → [기술 보고서](https://arxiv.org/abs/2512.13961) · [블로그](https://allenai.org/blog/olmo3)
- 7B와 32B. Base / Think(추론) / Instruct(대화·도구 사용) / RL-Zero 경로.
- 핵심 개념은 **모델 흐름(model flow)**: 최종 가중치만이 아니라 모델을 만드는 데 쓰인 모든 단계·체크포인트·데이터·의존성을 공개한다.
- 사전학습 3단계(넓은 데이터 → 어려운 데이터로 중간학습 → 긴 문맥 확장), 후처리 3단계(SFT → DPO → RLVR). 단계별 체크포인트가 공개되어 있다.
- 데이터: Dolma 3(사전학습), Dolci(후처리). 도구: OLMo-core(학습), open-instruct(후처리), OLMES(평가) 등.
- [OlmoTrace](https://allenai.org/blog/olmotrace): 모델 출력의 일부를 학습 데이터에서 찾아 보여 주는 도구.
- [7B Instruct 모델 카드](https://huggingface.co/allenai/Olmo-3-7B-Instruct)의 단계 표에서 각 단계 체크포인트로 이동할 수 있다.

**무엇을 볼 것인가**
- 보고서를 [워크북](../00_Foundations/10_paper-reading-workbook.md) 방식으로 읽되, **주장-증거 표**를 "설계 결정 → 근거(ablation)"로 만든다. 모델 보고서는 수십 개의 결정으로 이루어져 있다.
- 블로그의 비교 표: 비교 대상이 "완전 공개 모델"(Marin, Apertus)과 "가중치 공개 모델"(Qwen, Gemma, Llama)로 나뉘어 있다. 왜 나눠서 비교하는가?

**해 볼 것**
1. OLMo 2 1B의 Base와 Instruct에 같은 입력을 넣어 비교한다(CPU 가능, 느림).
2. Olmo 3 7B의 SFT / DPO / 최종 체크포인트 카드를 열어, 각 단계에서 무엇이 달라졌다고 적혀 있는지 표로 정리한다.
3. Ai2 Playground에서 OlmoTrace를 써 본다. 모델의 답 중 어느 부분이 학습 데이터에서 그대로 발견되는가?
4. 정독 과제: 보고서의 데이터 절만 골라 "출처별 비율 표"를 직접 다시 만든다.

---

## 7. Apertus

**무엇인가.** 스위스 AI 이니셔티브의 완전 공개 모델. **데이터 규정 준수**와 **다국어**를 앞세운다. → [논문](https://arxiv.org/abs/2509.14233) · [모델](https://huggingface.co/swiss-ai/Apertus-v1.5-8B)

**논문 초록에서 확인한 사실**
- 공개적으로 이용 가능한 데이터로만 사전학습. robots.txt의 수집 거부를 **소급해** 반영하고, 비허용 라이선스·유해·개인정보 콘텐츠를 필터링.
- 암기를 줄이기 위해 Goldfish 목적 함수를 사용.
- 1,800개가 넘는 언어의 15조 토큰, 약 40%가 비영어.
- 8B와 70B. 가중치 외에 개발 과정의 산출물을 허용적 라이선스로 공개.
- Hugging Face에는 2026년에 v1.5(8B·70B)와 단계별(`-SFT`, `-DPO`, `-RL`) 체크포인트가 올라와 있다.

**무엇을 볼 것인가**
- "어떤 데이터를 **쓰지 않았는가**"를 문서화한 방식. 대부분의 모델 문서에는 없는 내용이다.
- 암기 억제(Goldfish)가 성능에 준 영향에 대한 저자의 평가와 그 근거.

**해 볼 것:** 논문의 데이터 절과 Olmo 3·SmolLM3의 데이터 절을 나란히 놓고 "수집 원칙 / 필터 / 언어 구성"을 비교하는 표를 만든다.

---

## 8. Marin

**무엇인가.** 파운데이션 모델을 **공개적으로 개발하는** 연구 프로그램. → [저장소](https://github.com/marin-community/marin)

**저장소 README에서 확인한 사실**
- 핵심 가치는 "open development": 과정·실험·결정을 진행되는 대로 문서화하고, **실패한 실험도 기록의 일부**로 남긴다.
- Delphi: 계산 예산을 바꿔 가며 같은 레시피로 학습한 스케일링 실험 묶음(Pythia에서 영감). 모든 실행의 체크포인트, 데이터 혼합 파이프라인, 레시피 코드, 그림용 데이터를 공개.
- 이전에 8B·32B 모델을 학습했고 회고 문서가 저장소에 있다.

**무엇을 볼 것인가**
- GitHub 이슈로 관리되는 실험 계획과 결과. 논문에는 실리지 않는 "해 봤는데 안 된 것"을 읽을 수 있다.
- 회고 문서(retrospective): 무엇이 계획대로 됐고 무엇이 아니었나.

**해 볼 것:** 회고 문서 하나를 읽고 "다음에는 다르게 하겠다고 한 것" 세 가지를 뽑는다. 내 실험 기록에도 같은 칸을 만든다.

---

## 9. KORMo

**무엇인가.** KAIST 문화기술대학원 MLP 연구실이 처음부터(from scratch) 학습해 공개한 한국어·영어 10.8B 모델. 연구팀은 "비영어권 최초의 완전 오픈소스 LLM"이라고 밝힌다(연구팀 자신의 주장). → [기술 보고서](https://arxiv.org/abs/2510.09426) · [모델 카드](https://huggingface.co/KORMo-Team/KORMo-10B-sft) · [학습·추론 코드](https://github.com/MLP-Lab/KORMo-tutorial)

**모델 카드(2025-10)에서 확인한 사실**
- 10.8B 파라미터, 한국어·영어, Apache 2.0.
- 모델·학습 코드·학습 데이터·모델 체크포인트·튜토리얼을 공개. 공개한 학습 데이터는 총 3.7T 토큰 규모이며, 사전학습·사후학습·추론·강화학습용 한국어 데이터를 포함한다고 적혀 있다.
- 학부·석사생 8명이 만들었고, 보고서는 45쪽.
- 모델 카드의 벤치마크 표: 영어 평균 63.45, 한국어 평균 58.15 (같은 표의 Qwen3-8B는 67.90, 63.35).
- [오픈소스 포털의 한국어 소개 기사](https://www.oss.kr/pages/11/357)에 따르면 한국어 데이터의 약 68.74%를 합성 데이터로 만들어 사전학습에 썼다.

**무엇을 볼 것인가**
- **한국어로 공부할 수 있는 완전 공개 모델**이라는 점. 개발 과정을 한국어로 설명한 [세미나 영상](https://www.youtube.com/watch?v=yvLlNHFcT-Y)과 한국어 요약 슬라이드가 있다.
- 한국어 데이터가 부족한 문제를 합성 데이터로 푼 방식과 그 한계. OLMo·Apertus가 "있는 데이터를 거르고 섞는" 문제였다면, KORMo는 "없는 데이터를 만드는" 문제도 함께 풀었다.

**해 볼 것**
1. [체크리스트](01_openness-levels.md#4-판별-체크리스트-모델-하나에-10분) 10문항을 채우고, 가중치만 공개된 한국 모델(예: [K-EXAONE](https://arxiv.org/abs/2601.01739), [Kanana-2 개발기](https://tech.kakao.com/posts/807))과 나란히 비교한다.
2. 모델 카드가 안내하는 Colab 튜토리얼(QLoRA 지시 학습)로 [공부 방법](02_study-method.md) 6단계를 무료 GPU에서 해 본다.
3. 읽기·퀴즈 가이드: [PRACTICE.md의 KORMo 절](PRACTICE.md#kormo-한국어-완전-공개-모델)

---

## 비교군: 가중치만 공개된 모델

완전 공개 모델과 **무엇이 다른지 비교하기 위해** 알아 둔다. 추론과 미세조정 실습에는 이 모델들도 훌륭한 재료다.

| 계열 | 만든 곳 | 참고 문서 | 메모 (2026-11 Hugging Face 기준) |
|---|---|---|---|
| Llama | Meta | [*The Llama 3 Herd of Models*](https://arxiv.org/abs/2407.21783) | 자체 라이선스, 받으려면 승인 절차 |
| Gemma | Google | [*Gemma 4 Technical Report*](https://arxiv.org/abs/2607.02770) | Gemma 4 계열은 Apache-2.0 표시 |
| Qwen | Alibaba | [*Qwen3 Technical Report*](https://arxiv.org/abs/2505.09388) | Qwen3.8-27B는 Apache-2.0 표시 |
| DeepSeek | DeepSeek | [*DeepSeek-R1*](https://arxiv.org/abs/2501.12948), [*DeepSeek-V4*](https://arxiv.org/abs/2606.19348) | V4 계열은 MIT 표시 |
| gpt-oss | OpenAI | [*gpt-oss Model Card*](https://arxiv.org/abs/2508.10925) | Apache-2.0 표시 |
| K-EXAONE, A.X, Solar Open, Kanana, HyperCLOVA X SEED | LG AI연구원, SKT, Upstage, Kakao, NAVER | 각 모델 카드 | 한국어 모델. K-EXAONE 2.0·A.X K2는 Apache-2.0, 나머지는 자체 라이선스 표시 |

**비교 연습.** 위에서 하나, 완전 공개 모델에서 하나를 골라 [체크리스트](01_openness-levels.md#4-판별-체크리스트-모델-하나에-10분) 10문항을 나란히 채운다. 보고서에서 "학습 데이터"를 설명한 분량과 구체성을 비교해 본다.

## 다른 분야의 공개 모델

언어모델이 아니어도 같은 7단계로 공부할 수 있다.

| 분야 | 모델 | 공개된 것 | 연결되는 폴더 |
|---|---|---|---|
| 시계열 | [Chronos](https://github.com/amazon-science/chronos-forecasting) (Amazon) | 코드, 가중치(Apache-2.0), 데이터셋 모음(Hugging Face). 학습 절차까지 재현 가능한지는 체크리스트로 직접 확인 | [07_Time_Series](../07_Time_Series) — Lab 01에서 Chronos-2를 직접 돌린다 |
| 비전-언어 | [OpenCLIP](https://github.com/mlfoundations/open_clip) | 학습 코드, 공개 데이터(LAION)로 학습한 가중치 → [논문](https://arxiv.org/abs/2212.07143) | [05_Computer_Vision](../05_Computer_Vision) |
| 정형 데이터 | [TabICLv2](https://arxiv.org/abs/2602.11139) | 논문 제목이 "open tabular foundation model"을 내세운다. 공개 범위는 체크리스트로 직접 확인 | [02_Machine_Learning](../02_Machine_Learning) |
