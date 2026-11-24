# 실습 가이드 — Analytics Business

[필독 목록](READING_LIST.md)의 자료를 **읽고 → 해 보고 → 기억하는** 순서로 쓰는 문서. 읽는 요령은 [논문 읽기 워크북](../00_Foundations/10_paper-reading-workbook.md), 노트북 실행법은 [LABS.md](../LABS.md).

> 🇰🇷 영어가 부담되면 [READING_LIST.md](READING_LIST.md) 맨 위의 **🇰🇷 한국어로 시작하기** 표와 [KOREAN_START.md](../KOREAN_START.md)부터 본다. 아래 논문 가이드의 **🇰🇷 한국어로 먼저** 줄에 한국어 해설을 달아 두었다.

## 이 폴더의 실습
- 전용 노트북은 아직 없다. 아래 과제로 대신한다.
  - **Tidy data:** 가로로 넓은 표(예: 월별 매출이 열로 펼쳐진 표)를 `pandas.melt`로 길게 바꾸고 다시 `pivot`으로 되돌린다.
  - **심슨의 역설:** Bickel et al. (1975)의 버클리 입학 자료(R의 `UCBAdmissions`)로 전체 합격률과 학과별 합격률을 각각 계산해 결론이 뒤집히는 것을 확인한다.
  - **차트 고르기:** 같은 데이터를 파이 차트와 막대 차트로 그려 값의 순서를 맞히는 데 걸리는 시간을 비교한다(Cleveland & McGill).

## 자료 유형별 기본 과제
| 유형 | 할 일 | 남기는 것 |
|---|---|---|
| 논문 | 1차 읽기(10분) → 주장-증거 표 → 14개 질문 노트 | `summary.md` + 기억 점검 질문 3개 |
| 영상·강의 | 보기 전에 "알고 싶은 것 3개"를 적고, 본 뒤 답을 쓴다. 코드가 나오면 따라 치지 말고 **멈춘 뒤 먼저 써 본다** | 미디어 노트(`summary_media.md`) |
| 책·문서 | 한 장을 읽고 책을 덮은 채 핵심 3줄을 쓴다. 연습문제·예제 코드를 하나 이상 실행 | 장별 3줄 요약 |
| 블로그·뉴스 | 주장 1개와 근거 1개를 뽑고, 근거의 출처(원 논문·데이터)를 따라가 본다 | 한 줄 메모 + 원출처 링크 |
| 도구·저장소 | 공식 예제 하나를 실행하고, 내 데이터(또는 실습 노트북의 데이터)에 적용 | 실행한 코드 조각 |

## ★ 코어 자료 가이드
### Tidy Data
[DOI](https://doi.org/10.18637/jss.v059.i10)

- **이 논문이 답하는 질문:** 분석하기 쉬운 데이터의 표준 형태는 무엇인가.
- **🇰🇷 한국어로 먼저:** [R4DS 한국어 '데이터 타이디하게 하기'](https://bookdown.org/sulgi/r4ds/data-tidy.html)
- **읽기 가이드:** 세 원칙(변수=열, 관측=행, 관측 단위=표) → 지저분한 데이터의 다섯 유형 → 각 유형을 고치는 연산. 유형마다 내가 본 실제 표를 하나씩 떠올린다.
- **실습:** 위의 Tidy data 과제.

**기억 점검**
1. tidy data의 세 조건은?
2. 열 이름이 값인 표(예: 연도별 열)는 어떻게 고치나?

<details><summary>답 확인</summary>

1. 각 변수는 열, 각 관측은 행, 각 관측 단위 유형은 하나의 표.
2. melt(길게 만들기)로 '연도' 변수와 값 변수로 바꾼다.
</details>

### Measuring the User Experience on a Large Scale (HEART)
[DOI](https://doi.org/10.1145/1753326.1753687)

- **이 논문이 답하는 질문:** 대규모 서비스에서 사용자 경험을 어떤 지표로 잴 것인가.
- **읽기 가이드:** HEART 다섯 범주(Happiness, Engagement, Adoption, Retention, Task success)와 Goals–Signals–Metrics 절차. 짧은 논문이라 통독한다.
- **실습:** 자주 쓰는 앱 하나를 골라 Goals–Signals–Metrics 표를 만든다. 각 지표가 A/B 테스트에서 움직일 수 있는 지표인지도 적는다.

**기억 점검**
1. HEART의 다섯 범주는?
2. Goals–Signals–Metrics란?

<details><summary>답 확인</summary>

1. Happiness, Engagement, Adoption, Retention, Task success.
2. 목표를 먼저 정하고, 목표 달성을 나타내는 사용자 행동(신호)을 찾고, 그것을 측정 가능한 지표로 만든다.
</details>


## 그 밖의 자료
코어가 아닌 자료는 위의 "자료 유형별 기본 과제"를 따른다. 특정 자료의 읽기 가이드나 퀴즈가 필요하면 Claude에게 "○○ 실습 가이드 만들어줘"라고 요청하면 이 문서에 추가된다.
