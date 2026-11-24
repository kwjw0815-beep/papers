# 필독 자료 — Machine Learning

실무 정형 데이터(tabular)의 주력 무기. 트리·부스팅과 모델 해석이 중심.

> **읽는 법:** 영어가 부담되면 바로 아래 **🇰🇷 한국어로 시작하기**부터 본다. 영어 자료는 ①→②→③ 순서. **★** 는 먼저 볼 코어 자료, **🆕** 는 2025~2026년에 나온 자료다.  
> `선수 지식`의 문서를 먼저 훑고 오면 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.  
> 읽기 가이드·실습 과제·기억 점검 퀴즈는 [PRACTICE.md](PRACTICE.md), 실습 노트북은 [LABS.md](../LABS.md).

## 🇰🇷 한국어로 시작하기

영어 자료가 막막하면 여기서 시작한다. **★** 표시가 한국어로 먼저 볼 자료다. 번역서는 아래 영어 표의 원서와 내용이 같고, 영어 표에서 한국어판이나 한국어 해설이 있는 자료에는 🇰🇷 링크를 달아 두었다.

| 유형 | 자료 | 왜 보나 |
|---|---|---|
| 책·강의 | ★ 🆕 **[혼자 공부하는 머신러닝+딥러닝 (개정판)](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=361140631)**<br>박해선 · 한빛미디어 · 2025 · [저자 강의](https://www.youtube.com/playlist?list=PLJN246lAkhQihHwcbrZp9uuwgxQen5HS-) · [코드](https://github.com/rickiepark/hg-mldl2) | 가장 쉬운 한국어 입문서. 저자 직강 영상이 책 전체를 따라간다 |
| 강의 | ★ **[핵심 머신러닝 (재생목록)](https://www.youtube.com/playlist?list=PLpIPLT0Pf7IoTxTCi2MEQ94MZnHaxrP0j)**<br>김성범 교수 (고려대 산업경영공학부) | 회귀·트리·부스팅·SHAP·Transformer까지 개념을 깊이 있게 설명하는 한국어 강의 |
| 강의 | **[머신러닝 단기집중과정 (한국어)](https://developers.google.com/machine-learning/crash-course?hl=ko)**<br>Google | 아래 영어 목록 Machine Learning Crash Course의 한국어판 |
| 책 | 🆕 **[핸즈온 머신러닝 with 사이킷런, 파이토치](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=403219344)**<br>오렐리앙 제롱 · 박해선 옮김 · 한빛미디어 · 2026 · [코드](https://github.com/rickiepark/handson-mlp) | 아래 영어 목록 Hands-On ML (Scikit-Learn and PyTorch)의 한국어판 |
| 책 | **[머신 러닝 교과서: 파이토치 편](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=329349411)**<br>세바스찬 라시카 외 · 박해선 옮김 · 길벗 · 2023 | 이론과 코드를 균형 있게 다루는 교과서 |
| 책 | **[파이썬 머신러닝 완벽 가이드 (개정2판)](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=292601583)**<br>권철민 · 위키북스 · 2022 | 캐글 예제 중심으로 부스팅·피처 엔지니어링을 실전처럼 |
| 강의 | **[인공지능 및 기계학습 개론 1](https://www.youtube.com/playlist?list=PLzZ7PPT4KK5pc2YCyoJVITY897cbyUEHL)**<br>문일철 교수 (KAIST KOOC) | MLE·MAP·나이브 베이즈 등 확률적 관점의 정석 강의 |
| 강의 | **[Business Analytics (대학원)](https://www.youtube.com/playlist?list=PLetSlH8YjIfWMdw9AuLR5ybkVvGcoG2EW)**<br>강필성 교수 (DSBA 연구실) · [XGBoost 강의](https://www.youtube.com/watch?v=VHky3d_qZ_E) | 차원 축소·이상 탐지·앙상블을 대학원 수준으로 |
| 강의 | **[모두를 위한 머신러닝/딥러닝](https://hunkim.github.io/ml/)**<br>김성훈 교수 | 한국어 머신러닝 입문의 고전. 짧은 강의 여러 개 |

## 🌐 영어 자료

**먼저 읽을 것 (★)**: A Few Useful Things to Know About Machine Learning → XGBoost → SHAP

## ① 입문

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 강의 | **[Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course)**<br>Google<br>🇰🇷 [한국어판](https://developers.google.com/machine-learning/crash-course?hl=ko) | 짧은 시간에 ML 전체 흐름 잡기 (무료) | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 강의 | **[Machine Learning Specialization](https://www.coursera.org/specializations/machine-learning-introduction)**<br>Andrew Ng, Coursera | 가장 널리 쓰이는 ML 입문 강의 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 강의 | **[scikit-learn MOOC](https://inria.github.io/scikit-learn-mooc/)**<br>Inria (scikit-learn 개발팀) | 파이프라인·교차검증·튜닝을 올바르게 쓰는 법 (노트북 무료) | [ML 기초](../00_Foundations/04_ml-basics.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 실습 | **[Kaggle Learn](https://www.kaggle.com/learn)**<br>Kaggle | pandas·ML·피처 엔지니어링 짧은 실습 코스 | [도구](../00_Foundations/08_data-tools.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |

## ② 핵심

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 책 | **[Interpretable Machine Learning](https://christophm.github.io/interpretable-ml-book/)**<br>Christoph Molnar | 해석 기법(PDP, SHAP, LIME 등) 총정리 (웹 무료) | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 책 | 🆕 **[Hands-On Machine Learning with Scikit-Learn and PyTorch](https://github.com/ageron/handson-mlp)**<br>Aurélien Géron, 2025 · GitHub<br>🇰🇷 [한국어판](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=403219344) | 실습 중심 ML 입문서의 최신판 (노트북 공개) | [ML 기초](../00_Foundations/04_ml-basics.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[Random Forests](https://doi.org/10.1023/A:1010933404324)**<br>Breiman, 2001 · DOI | 배깅+랜덤 피처. 앙상블의 기본 | [ML 기초](../00_Foundations/04_ml-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Greedy Function Approximation: A Gradient Boosting Machine](https://doi.org/10.1214/aos/1013203451)**<br>Friedman, 2001 · DOI | 그래디언트 부스팅의 원전 | [ML 기초](../00_Foundations/04_ml-basics.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 논문 | **[Scikit-learn: Machine Learning in Python](https://arxiv.org/abs/1201.0490)**<br>Pedregosa et al., 2011 · arXiv 1201.0490 | 매일 쓰는 라이브러리의 설계 철학 (fit/predict 일관 API) | [ML 기초](../00_Foundations/04_ml-basics.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | ★ **[A Few Useful Things to Know About Machine Learning](https://doi.org/10.1145/2347736.2347755)**<br>Domingos, 2012 · DOI | 과적합·차원의 저주·피처 엔지니어링 등 "교과서에 없는 실전 지혜" 12가지 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | ★ **[XGBoost: A Scalable Tree Boosting System](https://arxiv.org/abs/1603.02754)**<br>Chen & Guestrin, 2016 · arXiv 1603.02754<br>🇰🇷 [DSBA XGBoost 강의](https://www.youtube.com/watch?v=VHky3d_qZ_E) · [김성범 교수 Boosting](https://www.youtube.com/watch?v=GciPwN2cde4) | 정형 데이터 대회·실무 표준. 정규화된 목적함수와 시스템 최적화 | [ML 기초](../00_Foundations/04_ml-basics.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 논문 | **[LightGBM: A Highly Efficient Gradient Boosting Decision Tree](https://papers.nips.cc/paper/2017/hash/6449f44a102fde848669bdd9eb6b76fa-Abstract.html)**<br>Ke et al., 2017 | GOSS·EFB로 대용량에서 빠른 부스팅 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | ★ **[A Unified Approach to Interpreting Model Predictions (SHAP)](https://arxiv.org/abs/1705.07874)**<br>Lundberg & Lee, 2017 · arXiv 1705.07874<br>🇰🇷 [김성범 교수 Shapley Value](https://www.youtube.com/watch?v=f2XqxOny3NA) | 모델 해석의 사실상 표준 | [ML 기초](../00_Foundations/04_ml-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[A Gentle Introduction to Conformal Prediction and Distribution-Free Uncertainty Quantification](https://arxiv.org/abs/2107.07511)**<br>Angelopoulos & Bates, 2021 · arXiv 2107.07511 | 어떤 모델이든 "보장된" 예측 구간을 붙이는 방법 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Tabular Data: Deep Learning is Not All You Need](https://arxiv.org/abs/2106.03253)**<br>Shwartz-Ziv & Armon, 2021 · arXiv 2106.03253 | 정형 데이터에서 XGBoost가 딥러닝보다 강하다는 재현 실험 | [ML 기초](../00_Foundations/04_ml-basics.md) · [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Leakage and the Reproducibility Crisis in ML-based Science](https://arxiv.org/abs/2207.07048)**<br>Kapoor & Narayanan, 2022 · arXiv 2207.07048 | 17개 분야 수백 편에서 발견된 데이터 누수 유형 정리 — 내 실험 점검표로 쓸 것 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | 🆕 **[Accurate predictions on small data with a tabular foundation model (TabPFN v2)](https://doi.org/10.1038/s41586-024-08328-6)**<br>Hollmann et al., Nature 2025 · DOI | 학습 없이 한 번의 forward pass로 예측하는 정형 데이터 파운데이션 모델 | [ML 기초](../00_Foundations/04_ml-basics.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |

## ③ 심화

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 책 | **[Fairness and Machine Learning](https://fairmlbook.org/)**<br>Barocas, Hardt, Narayanan | 공정성 지표와 그 한계 (웹 무료) | [ML 기초](../00_Foundations/04_ml-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) · [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 책 | **[Probabilistic Machine Learning](https://probml.github.io/pml-book/)**<br>Kevin Murphy | 확률 관점의 ML 백과사전 (PDF 무료) | [선형대수](../00_Foundations/01_linear-algebra.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 블로그 | 🆕 **[The state of Tabular Foundation Models (2026)](https://mindfulmodeler.substack.com/p/the-state-of-tabular-foundation-models)**<br>Christoph Molnar | 정형 파운데이션 모델의 현황을 실무자 눈높이로 정리 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[SMOTE: Synthetic Minority Over-sampling Technique](https://arxiv.org/abs/1106.1813)**<br>Chawla et al., 2002 · arXiv 1106.1813 | 불균형 데이터 처리의 고전 (한계도 함께 알아둘 것) | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Visualizing Data using t-SNE](https://www.jmlr.org/papers/v9/vandermaaten08a.html)**<br>van der Maaten & Hinton, 2008 | 고차원 시각화의 표준 기법 | [선형대수](../00_Foundations/01_linear-algebra.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **["Why Should I Trust You?": Explaining the Predictions of Any Classifier (LIME)](https://arxiv.org/abs/1602.04938)**<br>Ribeiro et al., 2016 · arXiv 1602.04938 | 국소 대리모델로 개별 예측 설명 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[CatBoost: unbiased boosting with categorical features](https://arxiv.org/abs/1706.09516)**<br>Prokhorenkova et al., 2017 · arXiv 1706.09516 | 범주형 변수 처리와 target leakage 방지 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[On Calibration of Modern Neural Networks](https://arxiv.org/abs/1706.04599)**<br>Guo et al., 2017 · arXiv 1706.04599 | 예측 확률이 실제 빈도와 맞는가 — temperature scaling | [ML 기초](../00_Foundations/04_ml-basics.md) · [신경망](../00_Foundations/05_neural-networks.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[UMAP: Uniform Manifold Approximation and Projection for Dimension Reduction](https://arxiv.org/abs/1802.03426)**<br>McInnes et al., 2018 · arXiv 1802.03426 | t-SNE보다 빠르고 전역 구조를 더 보존 | [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 논문 | **[Stop Explaining Black Box Machine Learning Models for High Stakes Decisions and Use Interpretable Models Instead](https://arxiv.org/abs/1811.10154)**<br>Rudin, 2018 · arXiv 1811.10154 | 사후 설명(SHAP·LIME)에 대한 가장 유명한 비판 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Optuna: A Next-generation Hyperparameter Optimization Framework](https://arxiv.org/abs/1907.10902)**<br>Akiba et al., 2019 · arXiv 1907.10902 | 하이퍼파라미터 탐색 도구의 표준 | [ML 기초](../00_Foundations/04_ml-basics.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[Revisiting Deep Learning Models for Tabular Data](https://arxiv.org/abs/2106.11959)**<br>Gorishniy et al., 2021 · arXiv 2106.11959 | 정형 데이터용 딥러닝(FT-Transformer)과 공정한 베이스라인 | [ML 기초](../00_Foundations/04_ml-basics.md) · [신경망](../00_Foundations/05_neural-networks.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Why do tree-based models still outperform deep learning on tabular data?](https://arxiv.org/abs/2207.08815)**<br>Grinsztajn et al., 2022 · arXiv 2207.08815 | 정형 데이터에서 트리가 여전히 강한 이유를 실험으로 분석 | [ML 기초](../00_Foundations/04_ml-basics.md) · [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[To SMOTE, or not to SMOTE?](https://arxiv.org/abs/2201.08528)**<br>Elor & Averbuch-Elor, 2022 · arXiv 2201.08528 | 강한 분류기에는 오버샘플링이 거의 도움이 안 된다는 반론 — SMOTE와 짝으로 읽기 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | 🆕 **[TabArena: A Living Benchmark for Machine Learning on Tabular Data](https://arxiv.org/abs/2506.16791)**<br>Erickson et al., 2025 · arXiv 2506.16791 | 정형 데이터 모델을 공정하게 비교하는 "살아 있는" 벤치마크 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | 🆕 **[TabPFN-3: Technical Report](https://arxiv.org/abs/2605.13986)**<br>Prior Labs, 2026 · arXiv 2605.13986 | 2026년 정형 파운데이션 모델의 현재 수준 (공급사 보고서임에 유의) | [ML 기초](../00_Foundations/04_ml-basics.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[TabICLv2: A better, faster, scalable, and open tabular foundation model](https://arxiv.org/abs/2602.11139)**<br>Qu et al., 2026 · arXiv 2602.11139 | 학습 코드까지 공개한 정형 파운데이션 모델 — TabPFN-3 보고서와 주장·평가 설정을 비교하며 읽기 | [ML 기초](../00_Foundations/04_ml-basics.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |

---
링크 확인: 2026-11-10(기존 자료), 2026-11-16~17(추가 자료), 2026-11-23~24(한국어 자료) — arXiv API · Crossref · HTTP 응답 · YouTube · GitHub로 제목 대조
