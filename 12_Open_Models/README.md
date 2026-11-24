# Open Models — 학습부터 가중치까지 전부 공개된 모델로 공부하기

**범위:** 학습 코드·학습 데이터·가중치(가능하면 중간 체크포인트와 학습 로그까지)가 공개된 AI 모델을 **직접 돌려 보고 뜯어보며** 공부하는 트랙. 다른 폴더가 "논문을 읽고 정리"하는 곳이라면, 여기는 **모델 한 개가 만들어지는 전 과정을 손으로 따라가는** 곳이다.

## 왜 완전 공개 모델인가

대부분의 유명한 모델은 결과물(가중치)이나 API만 공개한다. 그러면 "왜 이런 답을 하는가"라는 질문 앞에서 추측밖에 할 수 없다. 완전 공개 모델에서는 다음을 **직접 확인**할 수 있다.

| 궁금한 것 | 가중치만 공개된 모델 | 완전 공개 모델 |
|---|---|---|
| 어떤 데이터로 배웠나 | 논문의 한두 문단 | 데이터 자체를 내려받아 열어 본다 |
| 학습 설정(학습률, 배치, 스케줄)은 | 표 하나, 종종 일부만 | 설정 파일과 학습 스크립트 |
| 학습 중에 능력이 어떻게 생겼나 | 알 수 없음 | 중간 체크포인트를 불러 비교한다 |
| 논문의 숫자가 재현되나 | 추론 결과만 | 평가 코드까지 돌려 본다 |
| 한 요소를 바꾸면 어떻게 되나 | 불가능 | 작은 규모로 다시 학습해 본다 |

## 문서 안내 (읽는 순서)

| # | 문서 | 내용 |
|---|---|---|
| 1 | [01_openness-levels.md](01_openness-levels.md) | "공개"의 수준 구분하기 — 가중치 공개 vs 완전 공개, 판별 체크리스트, 모델별 분류표 |
| 2 | [02_study-method.md](02_study-method.md) | **공부 방법** — 7단계 절차, 단계별 산출물, 컴퓨터 사양별 경로 |
| 3 | [03_training-pipeline.md](03_training-pipeline.md) | **공부 내용** — 데이터에서 가중치까지 LLM이 만들어지는 전 과정과, 각 단계를 공개 모델에서 확인하는 곳 |
| 4 | [04_model-guides.md](04_model-guides.md) | 모델별 가이드 — nanoGPT·nanochat, TinyStories, Pythia, SmolLM2/3, OLMo 2/3, Apertus, Marin |
| 5 | [READING_LIST.md](READING_LIST.md) · [PRACTICE.md](PRACTICE.md) | 관련 논문·저장소 목록과 자료별 실습 과제 |
| 6 | [labs/](labs) | 실습 노트북 2개 (아래) |
| - | [모델 해부 노트 템플릿](../_templates/model_study.md) | 모델 하나를 공부할 때 채우는 양식 |

## 실습 노트북

모두 **노트북 CPU 또는 무료 Colab**에서 돌아가도록 작게 만들었다. 실행 결과가 포함되어 있어 돌리기 전에 먼저 읽어 볼 수 있다.

| 노트북 | 하는 일 | 대응하는 공부 단계 |
|---|---|---|
| [lab01_inspect_open_model](labs/lab01_inspect_open_model.ipynb) | 공개 가중치(SmolLM2-135M)를 내려받아 설정·파라미터·토크나이저·생성 과정을 하나씩 열어 본다 | 2·3단계 |
| [lab02_train_tiny_gpt_end_to_end](labs/lab02_train_tiny_gpt_end_to_end.ipynb) | 데이터 준비 → 토크나이저 → 모델 정의 → 학습 → 체크포인트 저장·재로딩 → 생성 → 모델 카드 작성까지 한 번에 | 4단계 |
| (노트북 없음) 5~7단계 | Pythia 체크포인트 비교, LoRA 미세조정, 오차 막대가 붙은 평가 — [02_study-method.md](02_study-method.md)의 절차대로 직접 작성 | 5·6·7단계 |

## 한눈에 보는 모델 지도

공개 수준과 크기에 따라 "내 컴퓨터로 어디까지 할 수 있는가"가 달라진다. (2026-11 기준, 각 모델의 공식 저장소·모델 카드·논문에서 확인)

| 모델 | 크기 | 공개된 것 | 내 컴퓨터에서 | 가장 좋은 용도 |
|---|---|---|---|---|
| **직접 학습하는 tiny GPT** ([lab02](labs/lab02_train_tiny_gpt_end_to_end.ipynb), [nanoGPT](https://github.com/karpathy/nanoGPT)) | 수십만~수천만 | 전부(내가 만든다) | CPU로 학습 | 전 과정을 처음 한 번 따라가기 |
| **TinyStories 모델** | 1M~33M | 데이터 + 가중치 | CPU로 추론·학습 | 작은 모델이 무엇을 배우는지 관찰 |
| **Pythia** (EleutherAI) | 70M~12B, 8종 | 데이터(순서까지) + 코드 + 가중치 + **체크포인트 154개씩** | 70M~410M은 CPU 추론 | 학습 과정에서 능력이 생기는 순서 관찰 |
| **SmolLM2 / SmolLM3** (Hugging Face) | 135M~3B | 가중치 + 데이터 구성 + 학습 설정·코드 + 중간 체크포인트 | 135M~360M은 CPU, 3B는 GPU | 현대적 소형 모델의 데이터·학습 단계 읽기 |
| **nanochat** (Karpathy) | 설정에 따라 | 코드 전부 + 공개 데이터 + 예시 가중치 | 축소판은 CPU, GPT-2급은 GPU 노드 대여 | 토크나이저부터 채팅 UI까지 한 저장소로 완주 |
| **OLMo 2 / Olmo 3** (Ai2) | 1B~32B | 데이터 + 코드 + 가중치 + 단계별 체크포인트 + 로그 | 1B는 CPU 추론, 그 이상은 GPU | 대규모 모델의 **전 과정 문서** 읽기, 출력→학습 데이터 추적 |
| **Apertus** (Swiss AI) | 8B, 70B | 데이터 파이프라인 + 코드 + 가중치 + 단계별 체크포인트 | GPU 필요 | 데이터 규정 준수·다국어 설계 사례 |
| **Marin** (Open Athena 외) | 다양 | 실험 계획·실패까지 공개 기록 | 문서 읽기 | "연구가 실제로 어떻게 진행되는가" 관찰 |
| **KORMo** (KAIST) | 10.8B | 데이터 + 코드 + 가중치 + 체크포인트 (한국어 데이터 포함) | 미세조정은 무료 Colab | **한국어로 공부할 수 있는** 완전 공개 모델 — 한국어 세미나·요약 자료가 있다 |
| *비교군:* Llama, Gemma, Qwen, DeepSeek, gpt-oss, K-EXAONE, A.X, Solar 등 | 수십억~수천억 | **가중치**(+ 보고서) | 작은 것만 | 추론·미세조정 실습, "공개 수준" 비교 |

자세한 분류 근거는 [01_openness-levels.md](01_openness-levels.md), 모델별 사용법은 [04_model-guides.md](04_model-guides.md).

## 추천 경로 (약 6주, 주 5~7시간)

| 주 | 할 일 | 산출물 |
|---|---|---|
| 1 | [01](01_openness-levels.md), [02](02_study-method.md) 읽기 → Karpathy *Deep Dive into LLMs* 영상 → [lab01](labs/lab01_inspect_open_model.ipynb) | SmolLM2-135M 해부 노트 (템플릿 1~3절) |
| 2 | [03](03_training-pipeline.md)의 데이터·토크나이저·구조 절 → [lab02](labs/lab02_train_tiny_gpt_end_to_end.ipynb) | 직접 학습한 모델의 손실 곡선 + 모델 카드 |
| 3 | nanoGPT 코드 읽기(`model.py` → `train.py`) → 셰익스피어 모델을 설정을 바꿔 가며 학습 | "바꾼 것 → 결과" 실험 기록 3줄 |
| 4 | *Pythia* 논문 읽기 → [공부 방법](02_study-method.md) 5단계(체크포인트 비교) | 체크포인트별 손실 그래프와 해석 |
| 5 | [03](03_training-pipeline.md)의 후처리·평가 절 → [공부 방법](02_study-method.md) 6·7단계(LoRA, 평가) → *SmolLM2* 논문 또는 SmolLM3 모델 카드 | 미세조정 전후 평가표(신뢰구간 포함) |
| 6 | *Olmo 3* 보고서를 [논문 읽기 워크북](../00_Foundations/10_paper-reading-workbook.md) 방식으로 정독 → 모델 해부 노트 완성 | `summary.md` + 모델 해부 노트 |
| 선택 | GPU를 빌려 nanochat `runs/speedrun.sh` 완주 | 내가 학습한 채팅 모델 |

## 정리 목록
| 날짜 | 주제 | 자료 유형 | 폴더 |
|---|---|---|---|
