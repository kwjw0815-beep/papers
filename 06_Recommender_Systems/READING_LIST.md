# 필독 자료 — Recommender Systems

협업 필터링 → 행렬 분해 → 딥러닝 랭킹 → 산업 사례 순서.

> **읽는 법:** ①→②→③ 순서. **★** 는 먼저 읽을 코어 자료, **🆕** 는 2025~2026년에 나온 자료다.  
> `선수 지식`의 문서를 먼저 훑고 오면 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.  
> 읽기 가이드·실습 과제·기억 점검 퀴즈는 [PRACTICE.md](PRACTICE.md), 실습 노트북은 [LABS.md](../LABS.md).

**먼저 읽을 것 (★)**: Matrix Factorization Techniques for Recommender Systems → Deep Neural Networks for YouTube Recommendations

## ① 입문

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 강의 | **[Recommendation Systems](https://developers.google.com/machine-learning/recommendation)**<br>Google | 후보 생성→랭킹 구조를 짧게 정리한 무료 코스 | [ML 기초](../00_Foundations/04_ml-basics.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 책 | **[Dive into Deep Learning — Recommender Systems 장](https://d2l.ai/chapter_recommender-systems/index.html)**<br>Zhang et al. | MF·AutoRec·BPR·시퀀스 추천을 코드와 함께 | [신경망](../00_Foundations/05_neural-networks.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 블로그 | **[System Design for Recommendations and Search](https://eugeneyan.com/writing/system-design-for-discovery/)**<br>Eugene Yan, 2021 | 오프라인/온라인 × 검색/랭킹 2×2 구조로 산업 추천 시스템 정리 | [ML 기초](../00_Foundations/04_ml-basics.md) |

## ② 핵심

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 도구 | **[Recommenders](https://github.com/recommenders-team/recommenders)**<br>recommenders-team (구 Microsoft) · GitHub | 주요 추천 알고리즘의 노트북 예제와 평가 코드 모음 | [ML 기초](../00_Foundations/04_ml-basics.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[Amazon.com Recommendations: Item-to-Item Collaborative Filtering](https://doi.org/10.1109/MIC.2003.1167344)**<br>Linden et al., 2003 · DOI | 아이템 기반 협업 필터링의 산업 적용 고전 | [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 논문 | **[Collaborative Filtering for Implicit Feedback Datasets](https://doi.org/10.1109/ICDM.2008.22)**<br>Hu, Koren, Volinsky, 2008 · DOI | 클릭·시청 같은 암묵적 피드백용 행렬 분해(ALS) — 현업 베이스라인 | [선형대수](../00_Foundations/01_linear-algebra.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 논문 | ★ **[Matrix Factorization Techniques for Recommender Systems](https://doi.org/10.1109/MC.2009.263)**<br>Koren et al., 2009 · DOI | Netflix Prize로 유명해진 행렬 분해 | [선형대수](../00_Foundations/01_linear-algebra.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 논문 | **[BPR: Bayesian Personalized Ranking from Implicit Feedback](https://arxiv.org/abs/1205.2618)**<br>Rendle et al., 2009 · arXiv 1205.2618 | 클릭 같은 암묵적 피드백으로 순위 학습 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 논문 | ★ **[Deep Neural Networks for YouTube Recommendations](https://doi.org/10.1145/2959100.2959190)**<br>Covington et al., 2016 · DOI | 후보 생성+랭킹 2단계 구조의 대표 사례 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Wide & Deep Learning for Recommender Systems](https://arxiv.org/abs/1606.07792)**<br>Cheng et al., 2016 · arXiv 1606.07792 | 암기(wide)+일반화(deep) 결합 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Sampling-Bias-Corrected Neural Modeling for Large Corpus Item Recommendations](https://doi.org/10.1145/3298689.3346996)**<br>Yi et al., 2019 · DOI | 투타워(two-tower) 검색 모델과 in-batch negative 보정 | [신경망](../00_Foundations/05_neural-networks.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Recommending What Video to Watch Next: A Multitask Ranking System](https://doi.org/10.1145/3298689.3346997)**<br>Zhao et al., 2019 · DOI | 여러 목표(클릭·시청·만족)를 함께 최적화하고 위치 편향을 보정 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[BERT4Rec: Sequential Recommendation with Bidirectional Encoder Representations from Transformer](https://arxiv.org/abs/1904.06690)**<br>Sun et al., 2019 · arXiv 1904.06690 | 가린 아이템 맞히기로 행동 시퀀스 학습 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Recommender Systems with Generative Retrieval (TIGER)](https://arxiv.org/abs/2305.05065)**<br>Rajput et al., 2023 · arXiv 2305.05065 | 아이템을 Semantic ID로 바꿔 "생성"하는 추천 — 생성형 추천의 출발점 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |

## ③ 심화

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 블로그 | 🆕 **[Improving Recommendation Systems & Search in the Age of LLMs](https://eugeneyan.com/writing/recsys-llm/)**<br>Eugene Yan, 2025 | LLM이 추천·검색 구조를 어떻게 바꾸는지 산업 논문 중심으로 정리 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[A Contextual-Bandit Approach to Personalized News Article Recommendation](https://arxiv.org/abs/1003.0146)**<br>Li et al., 2010 · arXiv 1003.0146 | 탐색-활용 균형(LinUCB)과 오프라인 평가 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[The Netflix Recommender System: Algorithms, Business Value, and Innovation](https://doi.org/10.1145/2843948)**<br>Gomez-Uribe & Hunt, 2015 · DOI | 추천을 비즈니스 가치·A/B 테스트와 연결해 설명 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | **[Neural Collaborative Filtering](https://arxiv.org/abs/1708.05031)**<br>He et al., 2017 · arXiv 1708.05031 | 내적을 신경망으로 대체 (아래 재현성 논문과 함께 읽기) | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[DeepFM: A Factorization-Machine based Neural Network for CTR Prediction](https://arxiv.org/abs/1703.04247)**<br>Guo et al., 2017 · arXiv 1703.04247 | CTR 예측의 대표 모델 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Self-Attentive Sequential Recommendation (SASRec)](https://arxiv.org/abs/1808.09781)**<br>Kang & McAuley, 2018 · arXiv 1808.09781 | 행동 순서를 Transformer로 모델링 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Are We Really Making Much Progress? A Worrying Analysis of Recent Neural Recommendation Approaches](https://arxiv.org/abs/1907.06902)**<br>Dacrema et al., 2019 · arXiv 1907.06902 | 잘 튜닝한 단순 모델이 최신 모델을 이긴다 — 비판적 읽기 훈련용 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Deep Learning Recommendation Model for Personalization and Recommendation Systems (DLRM)](https://arxiv.org/abs/1906.00091)**<br>Naumov et al., 2019 · arXiv 1906.00091 | 임베딩 테이블 + MLP — 산업 랭킹 모델의 기본형 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[LightGCN: Simplifying and Powering Graph Convolution Network for Recommendation](https://arxiv.org/abs/2002.02126)**<br>He et al., 2020 · arXiv 2002.02126 | 그래프 추천에서 불필요한 부품을 덜어낸 모델 | [선형대수](../00_Foundations/01_linear-algebra.md) · [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Neural Collaborative Filtering vs. Matrix Factorization Revisited](https://arxiv.org/abs/2005.09683)**<br>Rendle et al., 2020 · arXiv 2005.09683 | 잘 튜닝한 내적이 MLP를 이긴다 — NCF와 짝으로 읽기 | [ML 기초](../00_Foundations/04_ml-basics.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 논문 | **[Actions Speak Louder than Words: Trillion-Parameter Sequential Transducers for Generative Recommendations](https://arxiv.org/abs/2402.17152)**<br>Zhai et al. (Meta), 2024 · arXiv 2402.17152 | 추천을 시퀀스 생성 문제로 재정의한 대규모 산업 사례 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[OneRec: Unifying Retrieve and Rank with Generative Recommender and Iterative Preference Alignment](https://arxiv.org/abs/2502.18965)**<br>Kuaishou, 2025 · arXiv 2502.18965 | 검색·랭킹 다단계를 하나의 생성 모델로 통합한 산업 사례 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[Understanding Generative Recommendation with Semantic IDs from a Model-scaling View](https://arxiv.org/abs/2509.25522)**<br>2025 (KDD 2026) · arXiv 2509.25522 | Semantic ID 기반 생성 추천이 모델을 키워도 잘 안 느는 이유 분석 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[What Makes a Good Semantic ID for Generative Recommendation? A Reproducibility Study](https://arxiv.org/abs/2609.24430)**<br>2026 · arXiv 2609.24430 | Semantic ID 설계 선택을 재현 실험으로 점검 — 최신 유행을 비판적으로 읽기 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |

---
링크 확인: 2026-11-10(기존 자료), 2026-11-16~17(추가 자료) — arXiv API · Crossref · HTTP 응답 · YouTube · GitHub로 제목 대조
