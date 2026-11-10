# 00_Foundations — 자료를 이해하기 위한 기초 지식

각 분야 폴더의 `READING_LIST.md`에 있는 논문·강의를 읽을 때 **막히는 지점**을 풀어 주는 폴더.
교과서를 대체하려는 것이 아니라, "이 개념이 왜 필요하고 논문에서 어떻게 등장하는지"를 빠르게 잡는 것이 목표다.
각 문서는 **직관 → 정확한 정의 → 논문에서 만나는 모습 → 더 공부할 자료** 순서로 쓰여 있다.

## 문서 목록
| # | 문서 | 한 줄 설명 | 주로 필요한 분야 |
|---|---|---|---|
| 1 | [선형대수](01_linear-algebra.md) | 벡터·행렬·내적·고유값·SVD | 전 분야 (특히 03~06) |
| 2 | [미적분·최적화](02_calculus-optimization.md) | 기울기, 연쇄법칙, 경사하강법 | 02, 03, 04 |
| 3 | [확률·통계](03_probability-statistics.md) | 분포, 기댓값, 추정, 가설검정, 베이즈 | 01, 07, 08, 10 |
| 4 | [ML 기초](04_ml-basics.md) | 과적합, 검증, 평가 지표, 누수 | 02 이후 전부 |
| 5 | [신경망](05_neural-networks.md) | 층, 활성화, 손실, 역전파, 정규화 | 03, 04, 05 |
| 6 | [어텐션·Transformer](06_attention-transformer.md) | 임베딩, self-attention, 사전학습 | 04, 05, 06, 07 |
| 7 | [인과·실험 기초](07_causal-experiment-basics.md) | 상관≠인과, 무작위 배정, 교란 | 08, 10, 06 |
| 8 | [도구](08_data-tools.md) | Python, SQL, Git, 재현성 | 09, 10 및 모든 실습 |
| 9 | [논문 읽는 법](09_how-to-read-papers.md) | 3단계 읽기, 표·그림 읽기, 비판적 질문 | 전부 |
| - | [용어집](glossary.md) | 자주 나오는 용어 영-한 대조 | 전부 |

## 추천 학습 순서 (로드맵)

```
[0단계: 도구]      08 도구 ─ Python·SQL·Git
      │
[1단계: 수학]      01 선형대수 → 02 미적분·최적화 → 03 확률·통계
      │
[2단계: ML]        04 ML 기초 ──▶ 02_Machine_Learning, 01_Statistics_Math
      │                    └──▶ 07 인과·실험 ──▶ 08_Causal_Inference, 10_Analytics
      │
[3단계: DL]        05 신경망 ──▶ 03_Deep_Learning, 05_Computer_Vision
      │
[4단계: LLM]       06 어텐션·Transformer ──▶ 04_NLP_LLM, 06_RecSys, 07_Time_Series
      │
[상시]             09 논문 읽는 법 · 09_Data_Engineering_MLOps · 11_Career_Trends
```

- **수학을 다 끝내고 시작하려 하지 말 것.** 1단계는 각 문서의 "최소한 이것만" 절만 읽고 2단계로 넘어간 뒤, 논문에서 막힐 때 돌아온다.
- 데이터 **분석가** 지향이면 0 → 1(통계 위주) → 2 → 인과·실험 쪽을 깊게.
- **ML 엔지니어/리서치** 지향이면 0 → 1 → 2 → 3 → 4를 깊게.

## 처음 4주 제안 (하루 1~2시간 기준)
| 주 | 할 일 |
|---|---|
| 1 | 08 도구 확인 · 3Blue1Brown 선형대수 시리즈 · 01, 02 문서 |
| 2 | StatQuest로 통계 기초 · 03 문서 · Breiman "Two Cultures" 읽기 |
| 3 | 04 문서 · Google ML Crash Course · Domingos "A Few Useful Things" 읽고 노트 작성 |
| 4 | 05, 06 문서 · Karpathy micrograd 영상 · Illustrated Transformer → "Attention Is All You Need" 도전 |

모르는 것이 생기면 이 저장소에서 Claude에게 질문하면, 답변은 해당 자료의 `qna.md`에, 반복되는 기초 개념은 이 폴더에 보강된다.
