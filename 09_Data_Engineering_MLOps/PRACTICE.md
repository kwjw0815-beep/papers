# 실습 가이드 — Data Engineering MLOps

[필독 목록](READING_LIST.md)의 자료를 **읽고 → 해 보고 → 기억하는** 순서로 쓰는 문서. 읽는 요령은 [논문 읽기 워크북](../00_Foundations/10_paper-reading-workbook.md), 노트북 실행법은 [LABS.md](../LABS.md).

## 이 폴더의 실습
- 전용 노트북은 아직 없다. 아래 과제로 대신한다.
  - **SQL:** [Mode SQL Tutorial](https://mode.com/sql-tutorial/)의 윈도 함수 단원까지 풀고, "사용자별 첫 구매일과 7일 내 재구매 여부"를 쿼리 하나로 작성한다. [DuckDB](https://duckdb.org/docs/)를 쓰면 pandas DataFrame에 바로 SQL을 실행할 수 있다.
  - **파이프라인:** [ML Lab 01](../02_Machine_Learning/labs/lab01_validation_leakage_metrics.ipynb)의 전처리를 scikit-learn `Pipeline` 하나로 묶어 저장(`joblib`)하고 새 프로세스에서 불러 예측한다.

## 자료 유형별 기본 과제
| 유형 | 할 일 | 남기는 것 |
|---|---|---|
| 논문 | 1차 읽기(10분) → 주장-증거 표 → 14개 질문 노트 | `summary.md` + 기억 점검 질문 3개 |
| 영상·강의 | 보기 전에 "알고 싶은 것 3개"를 적고, 본 뒤 답을 쓴다. 코드가 나오면 따라 치지 말고 **멈춘 뒤 먼저 써 본다** | 미디어 노트(`summary_media.md`) |
| 책·문서 | 한 장을 읽고 책을 덮은 채 핵심 3줄을 쓴다. 연습문제·예제 코드를 하나 이상 실행 | 장별 3줄 요약 |
| 블로그·뉴스 | 주장 1개와 근거 1개를 뽑고, 근거의 출처(원 논문·데이터)를 따라가 본다 | 한 줄 메모 + 원출처 링크 |
| 도구·저장소 | 공식 예제 하나를 실행하고, 내 데이터(또는 실습 노트북의 데이터)에 적용 | 실행한 코드 조각 |

## ★ 코어 자료 가이드
### Hidden Technical Debt in Machine Learning Systems
[NeurIPS 2015](https://papers.nips.cc/paper/2015/hash/86df7dcfd896fcaf2674f757a2463eba-Abstract.html)

- **이 논문이 답하는 질문:** ML 시스템을 오래 운영할 때 비용을 키우는 것은 무엇인가.
- **읽기 가이드:** 유명한 그림(ML 코드는 전체의 작은 상자) → 부채의 종류를 목록으로: 얽힘(CACE), 숨은 피드백 루프, 데이터 의존성, 접착 코드, 설정 부채. 종류마다 "내 프로젝트의 예"를 하나씩 적는다.
- **실습:** 내가 만든 모델 하나(실습 노트북의 것이라도)를 골라, 입력 특성 하나의 분포가 바뀌면 무엇이 깨지는지, 그것을 어떻게 알아챌지 적는다.

**기억 점검**
1. CACE 원칙이란?
2. 숨은 피드백 루프의 예는?

<details><summary>답 확인</summary>

1. Changing Anything Changes Everything. 입력 하나를 바꾸면 다른 모든 것의 가중치·동작이 바뀐다.
2. 모델의 추천이 사용자 행동을 바꾸고, 그 행동 로그로 다시 모델을 학습하는 것.
</details>

### Rules of Machine Learning
[문서](https://developers.google.com/machine-learning/guides/rules-of-ml)

- **이 논문이 답하는 질문:** ML 제품을 만들 때 어떤 순서로 무엇을 해야 하는가.
- **읽기 가이드:** 단계별(ML 이전 → 첫 파이프라인 → 피처 엔지니어링 → 성장 둔화 이후)로 묶여 있다. 규칙 번호와 한 줄 요약만 표로 만들고, 지금 내 단계에 해당하는 규칙 5개를 고른다.
- **실습:** 실습 노트북 하나를 골라 "규칙 4: 첫 모델은 단순하게, 인프라를 제대로"의 관점에서 무엇이 인프라이고 무엇이 모델인지 나눠 본다.

**기억 점검**
1. ML을 쓰기 전에 먼저 해 볼 것은?
2. training-serving skew란?

<details><summary>답 확인</summary>

1. 휴리스틱으로 시작하고 지표를 먼저 설계·측정한다.
2. 학습 때와 서빙 때의 데이터·처리 방식 차이로 생기는 성능 차이.
</details>


## 그 밖의 자료
코어가 아닌 자료는 위의 "자료 유형별 기본 과제"를 따른다. 특정 자료의 읽기 가이드나 퀴즈가 필요하면 Claude에게 "○○ 실습 가이드 만들어줘"라고 요청하면 이 문서에 추가된다.
