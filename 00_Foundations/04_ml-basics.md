# ML 기초 (Machine Learning Basics)

## 왜 필요한가
모델 종류보다 중요한 것은 **"이 성능 숫자를 믿어도 되는가"**를 판단하는 능력이다. 과적합, 검증 방법, 평가 지표, 데이터 누수는 모든 ML 논문의 Experiments 절을 읽는 기본 문법이다.

## 최소한 이것만
| 개념 | 직관 | 정의 |
|---|---|---|
| 지도 / 비지도 학습 | 정답(label)이 있다 / 없다 | 회귀·분류 / 군집·차원축소 |
| 피처 (feature) / 라벨 | 입력 변수 / 맞히려는 값 | $X$, $y$ |
| 학습·검증·테스트 분할 | 연습문제 / 모의고사 / 수능 | train으로 학습, validation으로 튜닝, test는 **마지막에 한 번만** |
| 과적합 (overfitting) | 연습문제의 답을 외움 | train 성능 ≫ test 성능 |
| 과소적합 (underfitting) | 공부를 덜 함 | train 성능부터 낮음 |
| 편향-분산 트레이드오프 | 너무 단순(편향↑) vs 너무 민감(분산↑) | 기대 오차 = 편향² + 분산 + 잡음 |
| 교차검증 (k-fold CV) | 분할을 k번 바꿔 가며 평균 | 데이터가 적을 때 평가를 안정화 |
| 하이퍼파라미터 | 학습 전에 사람이 정하는 값 | 학습률, 트리 깊이, 정규화 강도 … |
| 베이스라인 (baseline) | 비교 기준이 되는 단순한 방법 | 베이스라인이 약하면 결과도 믿기 어렵다 |

## 평가 지표
**분류** — 혼동행렬(TP, FP, FN, TN)에서 출발
| 지표 | 식 | 언제 |
|---|---|---|
| Accuracy | (TP+TN)/전체 | 클래스가 균형일 때만 |
| Precision | TP/(TP+FP) | "양성이라고 한 것 중 진짜" — 오탐 비용이 클 때 (스팸) |
| Recall | TP/(TP+FN) | "진짜 양성 중 찾은 것" — 놓치면 안 될 때 (질병·사기) |
| F1 | 2PR/(P+R) | 둘의 조화평균 |
| ROC-AUC | 임계값 전체에 걸친 순위 품질 | 임계값과 무관한 비교 |
| PR-AUC | Precision-Recall 곡선 아래 넓이 | **불균형 데이터**에서 ROC-AUC보다 정직 |
| Log loss | 확률 예측의 품질 | 확률 자체가 중요할 때 (calibration) |

**회귀** — MAE(이상치에 강함), RMSE(큰 오차에 민감), R², MAPE(0 근처 값에 취약)
**랭킹·추천** — Precision@K, Recall@K, NDCG, MAP

## 데이터 누수 (leakage) — 가장 흔한 실수
예측 시점에 **알 수 없는 정보**가 학습에 들어가는 것. 성능이 비현실적으로 좋으면 먼저 의심한다.
- 전처리(스케일링, 결측 대체, target encoding)를 **분할 전에** 전체 데이터로 수행
- 시계열을 무작위로 분할 (미래로 과거를 예측)
- 같은 사용자·환자의 데이터가 train과 test에 모두 포함
- 라벨이 생긴 뒤에 기록되는 피처 사용 (예: 해지 예측에 "해지 상담 여부")

## 주요 모델 지도
| 모델 | 핵심 아이디어 | 강점 |
|---|---|---|
| 선형/로지스틱 회귀 | 피처의 가중합 | 해석 쉬움, 강한 베이스라인 |
| 결정 트리 | 질문을 반복해 분할 | 직관적, 단독으로는 과적합 |
| 랜덤 포레스트 (bagging) | 트리 여러 개를 **독립적으로** 만들어 평균 → 분산↓ | 튜닝 없이도 준수 |
| 그래디언트 부스팅 | 트리를 **순차적으로** 추가해 앞의 오차를 보정 → 편향↓ | 정형 데이터 최강 (XGBoost, LightGBM, CatBoost) |
| k-means / PCA | 군집 / 차원 축소 | 탐색적 분석 |
| 신경망 | → [신경망](05_neural-networks.md) | 이미지·텍스트·음성 |

## 논문 Experiments 절 체크리스트
- 베이스라인이 충분히 튜닝되었는가? (→ "Are We Really Making Much Progress?")
- test set으로 하이퍼파라미터를 고르지 않았는가?
- 개선 폭이 시드 변동(표준편차)보다 큰가?
- 데이터셋이 실제 문제와 닮았는가? ablation(구성요소 제거 실험)이 있는가?

## 더 공부할 자료
- 강의: [Google ML Crash Course](https://developers.google.com/machine-learning/crash-course) · [Andrew Ng ML Specialization](https://www.coursera.org/specializations/machine-learning-introduction)
- 논문: [A Few Useful Things to Know About ML](https://doi.org/10.1145/2347736.2347755)
- 책: [ISLR](https://www.statlearning.com/) 5(재표본), 8(트리)장
