# 필독 자료 — Machine Learning

실무 정형 데이터(tabular)의 주력 무기. 트리·부스팅과 모델 해석이 중심.

> **읽는 법:** ①→②→③ 순서. `선수 지식` 열의 링크를 먼저 훑고 오면 훨씬 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.

## ① 입문

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 강의 | Machine Learning Crash Course | Google | [링크](https://developers.google.com/machine-learning/crash-course) | 짧은 시간에 ML 전체 흐름 잡기 (무료) | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 강의 | Machine Learning Specialization | Andrew Ng, Coursera | [링크](https://www.coursera.org/specializations/machine-learning-introduction) | 가장 널리 쓰이는 ML 입문 강의 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 실습 | Kaggle Learn | Kaggle | [링크](https://www.kaggle.com/learn) | pandas·ML·피처 엔지니어링 짧은 실습 코스 | [도구](../00_Foundations/08_data-tools.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |

## ② 핵심

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 논문 | A Few Useful Things to Know About Machine Learning | Domingos, 2012 | [DOI](https://doi.org/10.1145/2347736.2347755) | 과적합·차원의 저주·피처 엔지니어링 등 "교과서에 없는 실전 지혜" 12가지 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | Random Forests | Breiman, 2001 | [DOI](https://doi.org/10.1023/A:1010933404324) | 배깅+랜덤 피처. 앙상블의 기본 | [ML 기초](../00_Foundations/04_ml-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | Greedy Function Approximation: A Gradient Boosting Machine | Friedman, 2001 | [DOI](https://doi.org/10.1214/aos/1013203451) | 그래디언트 부스팅의 원전 | [ML 기초](../00_Foundations/04_ml-basics.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 논문 | XGBoost: A Scalable Tree Boosting System | Chen & Guestrin, 2016 | [arXiv 1603.02754](https://arxiv.org/abs/1603.02754) | 정형 데이터 대회·실무 표준. 정규화된 목적함수와 시스템 최적화 | [ML 기초](../00_Foundations/04_ml-basics.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 논문 | LightGBM: A Highly Efficient Gradient Boosting Decision Tree | Ke et al., 2017 | [링크](https://papers.nips.cc/paper/2017/hash/6449f44a102fde848669bdd9eb6b76fa-Abstract.html) | GOSS·EFB로 대용량에서 빠른 부스팅 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | A Unified Approach to Interpreting Model Predictions (SHAP) | Lundberg & Lee, 2017 | [arXiv 1705.07874](https://arxiv.org/abs/1705.07874) | 모델 해석의 사실상 표준 | [ML 기초](../00_Foundations/04_ml-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 책 | Interpretable Machine Learning | Christoph Molnar | [링크](https://christophm.github.io/interpretable-ml-book/) | 해석 기법(PDP, SHAP, LIME 등) 총정리 (웹 무료) | [ML 기초](../00_Foundations/04_ml-basics.md) |

## ③ 심화

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 논문 | CatBoost: unbiased boosting with categorical features | Prokhorenkova et al., 2017 | [arXiv 1706.09516](https://arxiv.org/abs/1706.09516) | 범주형 변수 처리와 target leakage 방지 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | "Why Should I Trust You?": Explaining the Predictions of Any Classifier (LIME) | Ribeiro et al., 2016 | [arXiv 1602.04938](https://arxiv.org/abs/1602.04938) | 국소 대리모델로 개별 예측 설명 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | SMOTE: Synthetic Minority Over-sampling Technique | Chawla et al., 2002 | [arXiv 1106.1813](https://arxiv.org/abs/1106.1813) | 불균형 데이터 처리의 고전 (한계도 함께 알아둘 것) | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | Visualizing Data using t-SNE | van der Maaten & Hinton, 2008 | [링크](https://www.jmlr.org/papers/v9/vandermaaten08a.html) | 고차원 시각화의 표준 기법 | [선형대수](../00_Foundations/01_linear-algebra.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | UMAP: Uniform Manifold Approximation and Projection for Dimension Reduction | McInnes et al., 2018 | [arXiv 1802.03426](https://arxiv.org/abs/1802.03426) | t-SNE보다 빠르고 전역 구조를 더 보존 | [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 논문 | Why do tree-based models still outperform deep learning on tabular data? | Grinsztajn et al., 2022 | [arXiv 2207.08815](https://arxiv.org/abs/2207.08815) | 정형 데이터에서 트리가 여전히 강한 이유를 실험으로 분석 | [ML 기초](../00_Foundations/04_ml-basics.md) · [신경망](../00_Foundations/05_neural-networks.md) |

---
링크 확인일: 2026-11-10 (arXiv API · Crossref · HTTP 응답으로 제목 대조)
