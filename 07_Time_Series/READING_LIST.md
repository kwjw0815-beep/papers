# 필독 자료 — Time Series

고전 통계 모델을 먼저 익히고, 딥러닝이 정말 더 나은지 비판적으로 본다.

> **읽는 법:** ①→②→③ 순서. `선수 지식` 열의 링크를 먼저 훑고 오면 훨씬 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.

## ① 입문

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 책 | Forecasting: Principles and Practice (3rd ed.) | Hyndman & Athanasopoulos | [링크](https://otexts.com/fpp3/) | 시계열 예측의 표준 입문서 (웹 무료) | [확률·통계](../00_Foundations/03_probability-statistics.md) |

## ② 핵심

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 논문 | Forecasting at Scale (Prophet) | Taylor & Letham, 2018 | [DOI](https://doi.org/10.1080/00031305.2017.1380080) | 추세+계절성+휴일의 분해형 모델. 실무에서 널리 쓰임 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | Statistical and Machine Learning forecasting methods: Concerns and ways forward | Makridakis et al., 2018 | [DOI](https://doi.org/10.1371/journal.pone.0194889) | ML이 통계 모델보다 항상 낫지 않다는 실증 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | The M4 Competition: 100,000 time series and 61 forecasting methods | Makridakis et al., 2020 | [DOI](https://doi.org/10.1016/j.ijforecast.2019.04.014) | 대규모 예측 대회의 교훈 (앙상블·하이브리드) | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | Isolation Forest | Liu et al., 2008 | [DOI](https://doi.org/10.1109/ICDM.2008.17) | 이상 탐지의 기본 알고리즘 | [ML 기초](../00_Foundations/04_ml-basics.md) |

## ③ 심화

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 논문 | DeepAR: Probabilistic Forecasting with Autoregressive Recurrent Networks | Salinas et al., 2017 | [arXiv 1704.04110](https://arxiv.org/abs/1704.04110) | 여러 시계열을 함께 학습하는 확률적 예측 | [신경망](../00_Foundations/05_neural-networks.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | N-BEATS: Neural basis expansion analysis for interpretable time series forecasting | Oreshkin et al., 2019 | [arXiv 1905.10437](https://arxiv.org/abs/1905.10437) | 순수 딥러닝으로 M4 우승 모델을 넘은 구조 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | Temporal Fusion Transformers for Interpretable Multi-horizon Time Series Forecasting | Lim et al., 2019 | [arXiv 1912.09363](https://arxiv.org/abs/1912.09363) | 다양한 입력 변수를 다루는 해석 가능한 예측 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | Are Transformers Effective for Time Series Forecasting? | Zeng et al., 2022 | [arXiv 2205.13504](https://arxiv.org/abs/2205.13504) | 단순 선형 모델이 Transformer를 이긴다 — 비판적 읽기 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | A decoder-only foundation model for time-series forecasting (TimesFM) | Das et al., 2023 | [arXiv 2310.10688](https://arxiv.org/abs/2310.10688) | 시계열 파운데이션 모델 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |

---
링크 확인일: 2026-11-10 (arXiv API · Crossref · HTTP 응답으로 제목 대조)
