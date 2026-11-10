# 필독 자료 — Recommender Systems

협업 필터링 → 행렬 분해 → 딥러닝 랭킹 → 산업 사례 순서.

> **읽는 법:** ①→②→③ 순서. `선수 지식` 열의 링크를 먼저 훑고 오면 훨씬 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.

## ① 입문

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 강의 | Recommendation Systems | Google | [링크](https://developers.google.com/machine-learning/recommendation) | 후보 생성→랭킹 구조를 짧게 정리한 무료 코스 | [ML 기초](../00_Foundations/04_ml-basics.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |

## ② 핵심

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 논문 | Amazon.com Recommendations: Item-to-Item Collaborative Filtering | Linden et al., 2003 | [DOI](https://doi.org/10.1109/MIC.2003.1167344) | 아이템 기반 협업 필터링의 산업 적용 고전 | [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 논문 | Matrix Factorization Techniques for Recommender Systems | Koren et al., 2009 | [DOI](https://doi.org/10.1109/MC.2009.263) | Netflix Prize로 유명해진 행렬 분해 | [선형대수](../00_Foundations/01_linear-algebra.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 논문 | BPR: Bayesian Personalized Ranking from Implicit Feedback | Rendle et al., 2009 | [arXiv 1205.2618](https://arxiv.org/abs/1205.2618) | 클릭 같은 암묵적 피드백으로 순위 학습 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 논문 | Deep Neural Networks for YouTube Recommendations | Covington et al., 2016 | [DOI](https://doi.org/10.1145/2959100.2959190) | 후보 생성+랭킹 2단계 구조의 대표 사례 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | Wide & Deep Learning for Recommender Systems | Cheng et al., 2016 | [arXiv 1606.07792](https://arxiv.org/abs/1606.07792) | 암기(wide)+일반화(deep) 결합 | [신경망](../00_Foundations/05_neural-networks.md) |

## ③ 심화

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 논문 | The Netflix Recommender System: Algorithms, Business Value, and Innovation | Gomez-Uribe & Hunt, 2015 | [DOI](https://doi.org/10.1145/2843948) | 추천을 비즈니스 가치·A/B 테스트와 연결해 설명 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | Neural Collaborative Filtering | He et al., 2017 | [arXiv 1708.05031](https://arxiv.org/abs/1708.05031) | 내적을 신경망으로 대체 (아래 재현성 논문과 함께 읽기) | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | DeepFM: A Factorization-Machine based Neural Network for CTR Prediction | Guo et al., 2017 | [arXiv 1703.04247](https://arxiv.org/abs/1703.04247) | CTR 예측의 대표 모델 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | Self-Attentive Sequential Recommendation (SASRec) | Kang & McAuley, 2018 | [arXiv 1808.09781](https://arxiv.org/abs/1808.09781) | 행동 순서를 Transformer로 모델링 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | Are We Really Making Much Progress? A Worrying Analysis of Recent Neural Recommendation Approaches | Dacrema et al., 2019 | [arXiv 1907.06902](https://arxiv.org/abs/1907.06902) | 잘 튜닝한 단순 모델이 최신 모델을 이긴다 — 비판적 읽기 훈련용 | [ML 기초](../00_Foundations/04_ml-basics.md) |

---
링크 확인일: 2026-11-10 (arXiv API · Crossref · HTTP 응답으로 제목 대조)
