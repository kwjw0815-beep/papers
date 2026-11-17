# 필독 자료 — Time Series

고전 통계 모델을 먼저 익히고, 딥러닝이 정말 더 나은지 비판적으로 본다.

> **읽는 법:** ①→②→③ 순서. **★** 는 먼저 읽을 코어 자료, **🆕** 는 2025~2026년에 나온 자료다.  
> `선수 지식`의 문서를 먼저 훑고 오면 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.  
> 읽기 가이드·실습 과제·기억 점검 퀴즈는 [PRACTICE.md](PRACTICE.md), 실습 노트북은 [LABS.md](../LABS.md).

**먼저 읽을 것 (★)**: Statistical and Machine Learning forecasting methods: Concerns and ways forward → Are Transformers Effective for Time Series Forecasting?

## ① 입문

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 실습 | **[Time Series (Kaggle Learn)](https://www.kaggle.com/learn/time-series)** †<br>Kaggle | 추세·계절성·lag 피처·하이브리드 모델 짧은 실습 | [ML 기초](../00_Foundations/04_ml-basics.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 책 | **[Forecasting: Principles and Practice (3rd ed.)](https://otexts.com/fpp3/)**<br>Hyndman & Athanasopoulos | 시계열 예측의 표준 입문서 (웹 무료) | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 도구 | **[Nixtla (statsforecast · mlforecast · neuralforecast)](https://nixtlaverse.nixtla.io/)**<br>Nixtla | 통계·ML·딥러닝 예측을 같은 인터페이스로 — 베이스라인 만들기 가장 빠름 | [ML 기초](../00_Foundations/04_ml-basics.md) · [도구](../00_Foundations/08_data-tools.md) |

## ② 핵심

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 논문 | **[Another look at measures of forecast accuracy (MASE)](https://doi.org/10.1016/j.ijforecast.2006.03.001)**<br>Hyndman & Koehler, 2006 · DOI | MAPE의 문제와 MASE — 예측 평가 지표를 고르는 기준 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Isolation Forest](https://doi.org/10.1109/ICDM.2008.17)**<br>Liu et al., 2008 · DOI | 이상 탐지의 기본 알고리즘 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Forecasting at Scale (Prophet)](https://doi.org/10.1080/00031305.2017.1380080)**<br>Taylor & Letham, 2018 · DOI | 추세+계절성+휴일의 분해형 모델. 실무에서 널리 쓰임 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | ★ **[Statistical and Machine Learning forecasting methods: Concerns and ways forward](https://doi.org/10.1371/journal.pone.0194889)**<br>Makridakis et al., 2018 · DOI | ML이 통계 모델보다 항상 낫지 않다는 실증 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[The M4 Competition: 100,000 time series and 61 forecasting methods](https://doi.org/10.1016/j.ijforecast.2019.04.014)**<br>Makridakis et al., 2020 · DOI | 대규모 예측 대회의 교훈 (앙상블·하이브리드) | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[M5 accuracy competition: Results, findings, and conclusions](https://doi.org/10.1016/j.ijforecast.2021.11.013)**<br>Makridakis et al., 2022 · DOI | 소매 수요 예측 대회에서 LightGBM이 압도 — M4와 비교하며 읽기 | [ML 기초](../00_Foundations/04_ml-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[A Time Series is Worth 64 Words: Long-term Forecasting with Transformers (PatchTST)](https://arxiv.org/abs/2211.14730)**<br>Nie et al., 2022 · arXiv 2211.14730 | 패치 단위 입력과 채널 독립 — DLinear 비판에 대한 Transformer 쪽 답 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Chronos: Learning the Language of Time Series](https://arxiv.org/abs/2403.07815)**<br>Ansari et al. (Amazon), 2024 · arXiv 2403.07815 | 시계열을 토큰으로 바꿔 언어모델처럼 학습한 파운데이션 모델 (코드·가중치 공개) | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |

## ③ 심화

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 모델 | 🆕 **[TimesFM 3.0](https://huggingface.co/google/timesfm-3.0-pytorch)**<br>Google, 2026 | 2026년 공개된 시계열 파운데이션 모델 — 모델 카드 읽고 zero-shot 예측 실습 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[DeepAR: Probabilistic Forecasting with Autoregressive Recurrent Networks](https://arxiv.org/abs/1704.04110)**<br>Salinas et al., 2017 · arXiv 1704.04110 | 여러 시계열을 함께 학습하는 확률적 예측 | [신경망](../00_Foundations/05_neural-networks.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[N-BEATS: Neural basis expansion analysis for interpretable time series forecasting](https://arxiv.org/abs/1905.10437)**<br>Oreshkin et al., 2019 · arXiv 1905.10437 | 순수 딥러닝으로 M4 우승 모델을 넘은 구조 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Temporal Fusion Transformers for Interpretable Multi-horizon Time Series Forecasting](https://arxiv.org/abs/1912.09363)**<br>Lim et al., 2019 · arXiv 1912.09363 | 다양한 입력 변수를 다루는 해석 가능한 예측 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Current Time Series Anomaly Detection Benchmarks are Flawed and are Creating the Illusion of Progress](https://arxiv.org/abs/2009.13807)**<br>Wu & Keogh, 2020 · arXiv 2009.13807 | 이상 탐지 벤치마크의 결함 — 평가를 의심하는 법 | [ML 기초](../00_Foundations/04_ml-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Forecasting: theory and practice](https://arxiv.org/abs/2012.03854)**<br>Petropoulos et al., 2020 · arXiv 2012.03854 | 예측 분야 백과사전식 리뷰 (필요한 절만 찾아 읽기) | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | ★ **[Are Transformers Effective for Time Series Forecasting?](https://arxiv.org/abs/2205.13504)**<br>Zeng et al., 2022 · arXiv 2205.13504 | 단순 선형 모델이 Transformer를 이긴다 — 비판적 읽기 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[A decoder-only foundation model for time-series forecasting (TimesFM)](https://arxiv.org/abs/2310.10688)**<br>Das et al., 2023 · arXiv 2310.10688 | 시계열 파운데이션 모델 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Unified Training of Universal Time Series Forecasting Transformers (Moirai)](https://arxiv.org/abs/2402.02592)**<br>Woo et al. (Salesforce), 2024 · arXiv 2402.02592 | 임의 변수 수·주기를 다루는 범용 예측 모델 (데이터 LOTSA 공개) | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[GIFT-Eval: A Benchmark For General Time Series Forecasting Model Evaluation](https://arxiv.org/abs/2410.10393)**<br>Aksu et al., 2024 · arXiv 2410.10393 | 시계열 파운데이션 모델 비교의 표준 벤치마크 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Are Language Models Actually Useful for Time Series Forecasting?](https://arxiv.org/abs/2406.16964)**<br>Tan et al., 2024 · arXiv 2406.16964 | LLM을 빼도 성능이 같거나 낫다 — ablation으로 유행을 검증한 사례 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | 🆕 **[Chronos-2: From Univariate to Universal Forecasting](https://arxiv.org/abs/2510.15821)**<br>Ansari et al. (Amazon), 2025 · arXiv 2510.15821 | 다변량·공변량까지 zero-shot으로 다루는 후속 모델 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | 🆕 **[fev-bench: A Realistic Benchmark for Time Series Forecasting](https://arxiv.org/abs/2509.26468)**<br>Shchur et al., 2025 · arXiv 2509.26468 | 공변량 포함 현실적 과제 + 통계적으로 엄밀한 비교(신뢰구간) | [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |

† 표시는 이 환경에서 접속이 차단되어 자동 확인을 못 한 링크(널리 알려진 주소).

---
링크 확인: 2026-11-10(기존 자료), 2026-11-16~17(추가 자료) — arXiv API · Crossref · HTTP 응답 · YouTube · GitHub로 제목 대조
