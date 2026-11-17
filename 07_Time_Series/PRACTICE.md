# 실습 가이드 — Time Series

[필독 목록](READING_LIST.md)의 자료를 **읽고 → 해 보고 → 기억하는** 순서로 쓰는 문서. 읽는 요령은 [논문 읽기 워크북](../00_Foundations/10_paper-reading-workbook.md), 노트북 실행법은 [LABS.md](../LABS.md).

## 이 폴더의 실습
- [lab01_forecast_baselines_backtest](labs/lab01_forecast_baselines_backtest.ipynb) — 기준선·백테스트·MASE·Chronos-2

## 자료 유형별 기본 과제
| 유형 | 할 일 | 남기는 것 |
|---|---|---|
| 논문 | 1차 읽기(10분) → 주장-증거 표 → 14개 질문 노트 | `summary.md` + 기억 점검 질문 3개 |
| 영상·강의 | 보기 전에 "알고 싶은 것 3개"를 적고, 본 뒤 답을 쓴다. 코드가 나오면 따라 치지 말고 **멈춘 뒤 먼저 써 본다** | 미디어 노트(`summary_media.md`) |
| 책·문서 | 한 장을 읽고 책을 덮은 채 핵심 3줄을 쓴다. 연습문제·예제 코드를 하나 이상 실행 | 장별 3줄 요약 |
| 블로그·뉴스 | 주장 1개와 근거 1개를 뽑고, 근거의 출처(원 논문·데이터)를 따라가 본다 | 한 줄 메모 + 원출처 링크 |
| 도구·저장소 | 공식 예제 하나를 실행하고, 내 데이터(또는 실습 노트북의 데이터)에 적용 | 실행한 코드 조각 |

## ★ 코어 자료 가이드
### Statistical and Machine Learning forecasting methods: Concerns and ways forward
[DOI](https://doi.org/10.1371/journal.pone.0194889)

- **이 논문이 답하는 질문:** ML 예측 방법은 고전 통계 방법보다 정말 정확한가.
- **읽기 가이드:** 비교한 방법 목록, 데이터(M3의 월별 시계열), 지표(sMAPE, MASE), 예측 구간(1-step, multi-step)을 표로 정리한 뒤 결과 그림을 본다. "어떤 조건에서의 결론인가"(시계열 하나씩 따로 학습)를 반드시 적는다.
- **실습:** Lab 01의 2~4절과 7절. 내 결과에서 통계 모델과 ML의 순위는 어떻게 나왔나?

**기억 점검**
1. 이 논문의 결론이 성립한 조건은?
2. 기준선으로 꼭 넣어야 할 것은?

<details><summary>답 확인</summary>

1. 짧은 단변량 시계열을 하나씩 따로 학습하는 설정. 여러 시리즈를 함께 학습하고 외부 변수를 쓰는 설정(M5)에서는 결과가 달라졌다.
2. naive, seasonal naive 같은 단순 방법.
</details>

### Are Transformers Effective for Time Series Forecasting?
[arXiv 2205.13504](https://arxiv.org/abs/2205.13504)

- **이 논문이 답하는 질문:** 장기 예측에서 Transformer의 복잡한 구조가 정말 필요한가.
- **읽기 가이드:** 제안한 선형 모델의 구조(한 문단) → 주 결과 표 → lookback 길이를 늘렸을 때의 그림 → 순서를 섞어도 성능이 유지된다는 실험. 그다음 반론인 [PatchTST](https://arxiv.org/abs/2211.14730)의 초록을 읽는다.
- **실습:** Lab 01의 4절과 7절(이 데이터에서는 선형 모델이 기준선을 못 이긴다 → 왜일까).

**기억 점검**
1. 저자들이 Transformer의 약점으로 본 것은?
2. 이 결과를 일반화할 때 주의할 점은?

<details><summary>답 확인</summary>

1. 순서에 무관한 self-attention이 시간 순서 정보를 잃기 쉽다는 점.
2. 특정 장기 예측 벤치마크에서의 결과이며, 데이터·공변량·평가 방식이 달라지면 순위가 바뀐다.
</details>


## 그 밖의 자료
코어가 아닌 자료는 위의 "자료 유형별 기본 과제"를 따른다. 특정 자료의 읽기 가이드나 퀴즈가 필요하면 Claude에게 "○○ 실습 가이드 만들어줘"라고 요청하면 이 문서에 추가된다.
