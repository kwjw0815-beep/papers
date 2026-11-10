# 필독 자료 — Causal Inference Experimentation

데이터사이언티스트 실무·면접에서 가장 차별화되는 영역. A/B 테스트 → 관찰 데이터 인과추론 순.

> **읽는 법:** ①→②→③ 순서. `선수 지식` 열의 링크를 먼저 훑고 오면 훨씬 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.

## ① 입문

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 책 | Causal Inference for the Brave and True | Matheus Facure | [링크](https://matheusfacure.github.io/python-causality-handbook/landing-page.html) | Python 코드로 배우는 인과추론 (웹 무료) | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 책 | The Effect | Nick Huntington-Klein | [링크](https://theeffectbook.net/) | 수식을 최소화한 직관 중심 입문서 (웹 무료) | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 강의 | Introduction to Causal Inference | Brady Neal | [링크](https://www.bradyneal.com/causal-inference-course) | ML 관점의 인과추론 강의 (영상·교재 무료) | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |

## ② 핵심

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 책 | Trustworthy Online Controlled Experiments | Kohavi, Tang, Xu | [링크](https://experimentguide.com/) | A/B 테스트의 교과서 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | Controlled experiments on the web: survey and practical guide | Kohavi et al., 2009 | [DOI](https://doi.org/10.1007/s10618-008-0114-1) | 온라인 실험 실무 가이드의 고전 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | Online Controlled Experiments at Large Scale | Kohavi et al., 2013 | [DOI](https://doi.org/10.1145/2487575.2488217) | 대규모 실험 플랫폼 운영의 함정들 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | Improving the Sensitivity of Online Controlled Experiments by Utilizing Pre-Experiment Data (CUPED) | Deng et al., 2013 | [DOI](https://doi.org/10.1145/2433396.2433413) | 실험 전 데이터로 분산 줄이기 — 현업 표준 기법 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | Peeking at A/B Tests: Why it matters, and what to do about it | Johari et al., 2017 | [DOI](https://doi.org/10.1145/3097983.3097992) | 중간에 결과를 들여다보면 왜 틀리는가 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | Estimating causal effects of treatments in randomized and nonrandomized studies | Rubin, 1974 | [DOI](https://doi.org/10.1037/h0037350) | 잠재적 결과(potential outcomes) 프레임워크의 원전 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |

## ③ 심화

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 논문 | The central role of the propensity score in observational studies for causal effects | Rosenbaum & Rubin, 1983 | [DOI](https://doi.org/10.1093/biomet/70.1.41) | 성향점수의 원전 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | Synthetic Control Methods for Comparative Case Studies | Abadie et al., 2010 | [DOI](https://doi.org/10.1198/jasa.2009.ap08746) | 실험이 불가능할 때 가상의 대조군 만들기 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | Inferring causal impact using Bayesian structural time-series models (CausalImpact) | Brodersen et al., 2015 | [arXiv 1506.00356](https://arxiv.org/abs/1506.00356) | 시계열 기반 개입 효과 추정 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | Double/Debiased Machine Learning for Treatment and Causal Parameters | Chernozhukov et al., 2016 | [arXiv 1608.00060](https://arxiv.org/abs/1608.00060) | ML을 인과 효과 추정에 안전하게 쓰는 방법 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | Meta-learners for Estimating Heterogeneous Treatment Effects using Machine Learning | Künzel et al., 2017 | [arXiv 1706.03461](https://arxiv.org/abs/1706.03461) | S/T/X-learner — 업리프트 모델링의 기초 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | Estimation and Inference of Heterogeneous Treatment Effects using Random Forests | Wager & Athey, 2015 | [arXiv 1510.04342](https://arxiv.org/abs/1510.04342) | Causal Forest | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | Difference-in-Differences with Multiple Time Periods | Callaway & Sant'Anna, 2018 | [arXiv 1803.09015](https://arxiv.org/abs/1803.09015) | 처치 시점이 다른 경우의 현대적 DiD | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |

---
링크 확인일: 2026-11-10 (arXiv API · Crossref · HTTP 응답으로 제목 대조)
