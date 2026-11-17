# 실습 가이드 — Open Models

[필독 목록](READING_LIST.md)의 자료를 **읽고 → 해 보고 → 기억하는** 순서로 쓰는 문서. 읽는 요령은 [논문 읽기 워크북](../00_Foundations/10_paper-reading-workbook.md), 노트북 실행법은 [LABS.md](../LABS.md).

## 이 폴더의 실습
- [lab01_inspect_open_model](labs/lab01_inspect_open_model.ipynb) — 공개 가중치 해부
- [lab02_train_tiny_gpt_end_to_end](labs/lab02_train_tiny_gpt_end_to_end.ipynb) — 직접 학습부터 모델 카드까지
- 체크포인트 비교·미세조정·평가는 [02_study-method.md](02_study-method.md)의 5~7단계 과제로 진행한다(Pythia `revision="step…"`).

## 자료 유형별 기본 과제
| 유형 | 할 일 | 남기는 것 |
|---|---|---|
| 논문 | 1차 읽기(10분) → 주장-증거 표 → 14개 질문 노트 | `summary.md` + 기억 점검 질문 3개 |
| 영상·강의 | 보기 전에 "알고 싶은 것 3개"를 적고, 본 뒤 답을 쓴다. 코드가 나오면 따라 치지 말고 **멈춘 뒤 먼저 써 본다** | 미디어 노트(`summary_media.md`) |
| 책·문서 | 한 장을 읽고 책을 덮은 채 핵심 3줄을 쓴다. 연습문제·예제 코드를 하나 이상 실행 | 장별 3줄 요약 |
| 블로그·뉴스 | 주장 1개와 근거 1개를 뽑고, 근거의 출처(원 논문·데이터)를 따라가 본다 | 한 줄 메모 + 원출처 링크 |
| 도구·저장소 | 공식 예제 하나를 실행하고, 내 데이터(또는 실습 노트북의 데이터)에 적용 | 실행한 코드 조각 |

## ★ 코어 자료 가이드
### Pythia
[arXiv 2304.01373](https://arxiv.org/abs/2304.01373)

- **이 논문이 답하는 질문:** 학습 과정과 모델 크기에 따라 언어모델이 어떻게 달라지는지 연구할 수 있는 통제된 모델 묶음을 만들 수 있는가.
- **읽기 가이드:** 모델·데이터·체크포인트 설계(무엇을 같게 맞췄는가) → 사례 연구 세 개 중 하나만 골라 정독. [04_model-guides.md](04_model-guides.md)의 Pythia 절과 함께.
- **실습:** step 0, 1000, 10000, 143000 체크포인트를 불러 같은 문장들의 손실을 비교한다(공부 방법 5단계).

**기억 점검**
1. 모든 모델이 공유하는 것은?
2. 체크포인트는 몇 개이고 언제 저장됐나?

<details><summary>답 확인</summary>

1. 같은 데이터를 같은 순서로 학습했다.
2. 모델당 154개. step 0, 1, 2, 4, …, 512, 1000, 이후 1,000 스텝마다.
</details>

### Olmo 3
[arXiv 2512.13961](https://arxiv.org/abs/2512.13961)

- **이 논문이 답하는 질문:** 최종 가중치뿐 아니라 모델을 만드는 전 과정(model flow)을 공개하면 무엇이 가능해지는가.
- **읽기 가이드:** [Ai2 블로그](https://allenai.org/blog/olmo3)로 전체 구조를 잡은 뒤 보고서의 데이터 절과 학습 단계 절을 읽는다. 주장-증거 표를 "설계 결정 → 근거"로 만든다.
- **실습:** [01_openness-levels.md](01_openness-levels.md)의 체크리스트 10문항을 Olmo 3에 대해 채우고, 가중치만 공개된 모델 하나와 나란히 비교한다.

**기억 점검**
1. 사전학습과 후처리의 단계는?
2. fully open과 open-weight의 차이는?

<details><summary>답 확인</summary>

1. 사전학습: 넓은 데이터 → 중간학습 → 긴 문맥 확장. 후처리: SFT → DPO → RLVR.
2. fully open은 학습 데이터·코드·가중치(와 체크포인트)를 모두 공개, open-weight는 가중치 중심.
</details>

### nanoGPT · nanochat
읽기·실습 과제는 [04_model-guides.md](04_model-guides.md)의 1절과 5절에 있다. 핵심 과제: `runs/speedrun.sh`(nanochat)의 각 줄이 [03_training-pipeline.md](03_training-pipeline.md)의 어느 단계인지 주석을 단다.

## 그 밖의 자료
코어가 아닌 자료는 위의 "자료 유형별 기본 과제"를 따른다. 특정 자료의 읽기 가이드나 퀴즈가 필요하면 Claude에게 "○○ 실습 가이드 만들어줘"라고 요청하면 이 문서에 추가된다.
