# 인과·실험 기초 (Causality & Experimentation)

## 왜 필요한가
회사에서 데이터사이언티스트가 받는 질문은 대부분 인과 질문이다. "이 기능이 매출을 **올렸는가**?", "쿠폰을 **주면** 재구매가 늘까?". 예측 모델은 "무엇이 일어날지"를 말하지만 "무엇을 **하면** 어떻게 되는지"는 말해 주지 않는다.

## 최소한 이것만
| 개념 | 직관 | 정의 |
|---|---|---|
| 상관 ≠ 인과 | 아이스크림 판매와 익사 사고는 함께 늘지만 원인은 더위 | |
| 교란변수 (confounder) | 처치와 결과 **둘 다**에 영향을 주는 제3의 변수 | 위 예의 "기온" |
| 처치 (treatment) / 대조 (control) | 개입을 받은 집단 / 받지 않은 집단 | $T=1$ / $T=0$ |
| 잠재적 결과 (potential outcomes) | 같은 사람이 처치를 받았을 때와 안 받았을 때의 결과 | $Y(1)$, $Y(0)$ |
| 인과추론의 근본 문제 | 한 사람에게서 둘을 동시에 관측할 수 없다 | 반사실(counterfactual)은 항상 결측 |
| 평균 처치 효과 (ATE) | 개인 효과는 몰라도 평균은 추정 가능 | $E[Y(1)-Y(0)]$ |
| 무작위 배정 (randomization) | 동전 던지기로 배정하면 두 집단이 평균적으로 같아짐 → 교란 제거 | RCT, A/B 테스트 |
| 선택 편향 (selection bias) | 처치를 받은 사람이 원래부터 다른 사람들 | 예: 쿠폰을 쓴 사람은 원래 충성 고객 |

## A/B 테스트 한 사이클
1. **가설·지표 정의** — 핵심 지표(OEC) 1개 + 가드레일 지표. 실험 전에 정한다.
2. **표본 크기 계산** — 최소 검출 효과(MDE), 유의수준 $\alpha$, 검정력(보통 80%)으로 결정. → [확률·통계](03_probability-statistics.md)
3. **무작위 배정** — 단위(사용자/세션)를 정하고 해시로 분할.
4. **실행** — 정해진 기간(보통 요일 효과를 고려해 1~2주 단위) 동안.
5. **분석** — 차이, 신뢰구간, p-value. 세그먼트별 확인은 탐색용으로만.
6. **결정**

**자주 빠지는 함정**
| 함정 | 설명 | 관련 자료 |
|---|---|---|
| Peeking | 유의해질 때까지 계속 들여다보고 멈춤 → 1종 오류 폭증 | Johari et al., 2017 |
| 다중 비교 | 지표·세그먼트를 많이 보면 우연히 유의한 것이 나옴 | Benjamini-Hochberg |
| SRM (sample ratio mismatch) | 50:50이어야 할 배정 비율이 어긋남 → 실험이 고장났다는 신호 | Kohavi et al. |
| Novelty effect | 새로워서 잠깐 반응한 것 | |
| 간섭 (interference) | 한 사용자의 처치가 다른 사용자에게 영향 (마켓·소셜) | SUTVA 위반 |
| 분산이 커서 검출 불가 | 실험 전 데이터로 분산을 줄인다 | CUPED |

## 실험을 할 수 없을 때 — 관찰 데이터 인과추론
| 방법 | 아이디어 | 핵심 가정 |
|---|---|---|
| 회귀 조정 / 매칭 / 성향점수 | 교란변수가 비슷한 사람끼리 비교 | 교란변수를 **모두** 관측했다 |
| 이중차분법 (DiD) | 처치군의 전후 변화 − 대조군의 전후 변화 | 평행 추세 (처치가 없었다면 같이 움직였을 것) |
| 통제집단합성법 (Synthetic Control) | 여러 대조 단위를 가중합해 "가상의 처치군" 생성 | 개입 전 추세를 잘 재현 |
| 회귀불연속 (RDD) | 기준점 바로 위·아래는 사실상 무작위 | 기준점 근처에서 조작 없음 |
| 도구변수 (IV) | 처치에만 영향을 주는 외부 변수 이용 | 도구가 결과에 직접 영향 없음 |
| 업리프트 / CATE | 사람마다 다른 처치 효과 추정 | meta-learner, causal forest |

모든 방법은 **검증할 수 없는 가정**에 의존한다. 논문을 읽을 때 "어떤 가정을 했고 그것이 그럴듯한가"를 가장 먼저 본다.

**DAG (인과 그래프)** — 변수 간 인과 관계를 화살표로 그린 것. 무엇을 통제해야 하고 무엇을 통제하면 안 되는지(collider, mediator) 판단하는 도구.

## 더 공부할 자료
- 책(무료): [Causal Inference for the Brave and True](https://matheusfacure.github.io/python-causality-handbook/landing-page.html) · [The Effect](https://theeffectbook.net/) · [Causal Inference: The Mixtape](https://mixtape.scunning.com/)
- 책: [Trustworthy Online Controlled Experiments](https://experimentguide.com/)
- 강의: [Brady Neal — Introduction to Causal Inference](https://www.bradyneal.com/causal-inference-course)
