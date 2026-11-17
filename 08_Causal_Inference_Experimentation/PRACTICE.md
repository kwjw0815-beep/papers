# 실습 가이드 — Causal Inference Experimentation

[필독 목록](READING_LIST.md)의 자료를 **읽고 → 해 보고 → 기억하는** 순서로 쓰는 문서. 읽는 요령은 [논문 읽기 워크북](../00_Foundations/10_paper-reading-workbook.md), 노트북 실행법은 [LABS.md](../LABS.md).

## 이 폴더의 실습
- [lab01_ab_test_simulation](labs/lab01_ab_test_simulation.ipynb) — 검정력·peeking·CUPED·SRM
- 관찰 데이터 인과추론은 노트북이 아직 없다. *[Causal Inference for the Brave and True](https://matheusfacure.github.io/python-causality-handbook/landing-page.html)* 의 성향점수·DiD 장을 코드와 함께 실행하는 것으로 대신한다.

## 자료 유형별 기본 과제
| 유형 | 할 일 | 남기는 것 |
|---|---|---|
| 논문 | 1차 읽기(10분) → 주장-증거 표 → 14개 질문 노트 | `summary.md` + 기억 점검 질문 3개 |
| 영상·강의 | 보기 전에 "알고 싶은 것 3개"를 적고, 본 뒤 답을 쓴다. 코드가 나오면 따라 치지 말고 **멈춘 뒤 먼저 써 본다** | 미디어 노트(`summary_media.md`) |
| 책·문서 | 한 장을 읽고 책을 덮은 채 핵심 3줄을 쓴다. 연습문제·예제 코드를 하나 이상 실행 | 장별 3줄 요약 |
| 블로그·뉴스 | 주장 1개와 근거 1개를 뽑고, 근거의 출처(원 논문·데이터)를 따라가 본다 | 한 줄 메모 + 원출처 링크 |
| 도구·저장소 | 공식 예제 하나를 실행하고, 내 데이터(또는 실습 노트북의 데이터)에 적용 | 실행한 코드 조각 |

## ★ 코어 자료 가이드
### Controlled experiments on the web: survey and practical guide
[DOI](https://doi.org/10.1007/s10618-008-0114-1)

- **이 논문이 답하는 질문:** 온라인 실험을 올바르게 설계·실행·분석하려면 무엇을 알아야 하는가.
- **읽기 가이드:** 긴 논문이다. 용어 정의 → 표본 크기·검정력 → 한계 → 실행상의 교훈 순으로 **필요한 절만** 읽는다. 읽으면서 "우리 서비스라면"으로 바꿔 적는다.
- **실습:** Lab 01의 1~2절, 직접 해보기 1(실험 기간)과 3(분석 단위).

**기억 점검**
1. OEC란?
2. A/A 테스트는 왜 하나?

<details><summary>답 확인</summary>

1. Overall Evaluation Criterion. 실험의 성패를 판단할 하나의(또는 합성된) 핵심 지표로, 실험 전에 정한다.
2. 실험 시스템 자체를 검증하기 위해(차이가 없어야 하고 p-value가 균등해야 한다).
</details>

### CUPED
[DOI](https://doi.org/10.1145/2433396.2433413)

- **이 논문이 답하는 질문:** 실험 전 데이터를 이용해 같은 표본으로 더 작은 효과를 검출할 수 있는가.
- **읽기 가이드:** 통제변량(control variates)에서 식을 유도하는 부분 → 어떤 공변량이 좋은가 → 실제 실험에서의 분산 감소율. θ의 식을 수식 읽기 4단계로.
- **실습:** Lab 01의 5절과 직접 해보기 2.

**기억 점검**
1. CUPED 조정식은?
2. 분산은 얼마나 줄어드나? 편향이 없는 이유는?

<details><summary>답 확인</summary>

1. Y − θ(X − X̄), θ = Cov(X,Y)/Var(X).
2. (1 − ρ²)배. X가 실험 전에 정해져 무작위 배정과 독립이기 때문.
</details>

### Peeking at A/B Tests
[DOI](https://doi.org/10.1145/3097983.3097992)

- **이 논문이 답하는 질문:** 사용자가 실험 중간에 계속 결과를 본다는 현실에서 어떻게 유효한 추론을 할 것인가.
- **읽기 가이드:** 문제 제기(왜 사람들은 들여다보는가) → always-valid p-value의 정의 → mSPRT. 증명은 건너뛰고 '무엇을 보장하는가'만 적는다. Evan Miller의 글을 먼저 읽으면 쉽다.
- **실습:** Lab 01의 3~4절.

**기억 점검**
1. 매일 보고 유의하면 멈추면 오탐률은?
2. always-valid p-value의 대가는?

<details><summary>답 확인</summary>

1. 5%보다 훨씬 커진다(Lab의 설정에서 약 23%).
2. 같은 표본에서 고정 표본 검정보다 검정력이 낮다.
</details>


## 그 밖의 자료
코어가 아닌 자료는 위의 "자료 유형별 기본 과제"를 따른다. 특정 자료의 읽기 가이드나 퀴즈가 필요하면 Claude에게 "○○ 실습 가이드 만들어줘"라고 요청하면 이 문서에 추가된다.
