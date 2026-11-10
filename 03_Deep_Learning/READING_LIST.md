# 필독 자료 — Deep Learning

신경망을 학습시키는 핵심 부품(역전파, 최적화, 정규화, 잔차연결)을 이해한다.

> **읽는 법:** ①→②→③ 순서. `선수 지식` 열의 링크를 먼저 훑고 오면 훨씬 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.

## ① 입문

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 영상 | Neural Networks (시리즈) | 3Blue1Brown | [링크](https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi) | 신경망·경사하강·역전파를 시각적으로 설명 | [신경망](../00_Foundations/05_neural-networks.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 영상 | The spelled-out intro to neural networks and backpropagation: building micrograd | Andrej Karpathy | [링크](https://www.youtube.com/watch?v=VMj-3S1tku0) | 역전파를 100줄 코드로 직접 구현 | [신경망](../00_Foundations/05_neural-networks.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 강의 | Practical Deep Learning for Coders | fast.ai | [링크](https://course.fast.ai/) | 코드부터 시작하는 top-down 방식 (무료) | [도구](../00_Foundations/08_data-tools.md) · [신경망](../00_Foundations/05_neural-networks.md) |

## ② 핵심

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 책 | Dive into Deep Learning | Zhang et al. | [링크](https://d2l.ai/) | 수식·코드·설명이 함께 있는 무료 교재 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 책 | Understanding Deep Learning | Simon Prince | [링크](https://udlbook.github.io/udlbook/) | 최신 내용까지 담은 그림 중심 교재 (PDF 무료) | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | Deep learning | LeCun, Bengio, Hinton, 2015 | [DOI](https://doi.org/10.1038/nature14539) | 딥러닝 전체를 조망하는 Nature 리뷰 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | Learning representations by back-propagating errors | Rumelhart, Hinton, Williams, 1986 | [DOI](https://doi.org/10.1038/323533a0) | 역전파의 원전 (3쪽) | [신경망](../00_Foundations/05_neural-networks.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 논문 | Dropout: A Simple Way to Prevent Neural Networks from Overfitting | Srivastava et al., 2014 | [링크](https://jmlr.org/papers/v15/srivastava14a.html) | 가장 유명한 정규화 기법 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | Adam: A Method for Stochastic Optimization | Kingma & Ba, 2014 | [arXiv 1412.6980](https://arxiv.org/abs/1412.6980) | 기본 옵티마이저 | [미적분·최적화](../00_Foundations/02_calculus-optimization.md) · [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift | Ioffe & Szegedy, 2015 | [arXiv 1502.03167](https://arxiv.org/abs/1502.03167) | 깊은 망 학습 안정화 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | Deep Residual Learning for Image Recognition (ResNet) | He et al., 2015 | [arXiv 1512.03385](https://arxiv.org/abs/1512.03385) | 잔차 연결 — Transformer까지 이어지는 핵심 아이디어 | [신경망](../00_Foundations/05_neural-networks.md) |

## ③ 심화

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 논문 | Long Short-Term Memory | Hochreiter & Schmidhuber, 1997 | [DOI](https://doi.org/10.1162/neco.1997.9.8.1735) | 순환신경망의 기울기 소실 해결 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | Generative Adversarial Networks | Goodfellow et al., 2014 | [arXiv 1406.2661](https://arxiv.org/abs/1406.2661) | 생성 모델의 전환점 | [신경망](../00_Foundations/05_neural-networks.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | Auto-Encoding Variational Bayes (VAE) | Kingma & Welling, 2013 | [arXiv 1312.6114](https://arxiv.org/abs/1312.6114) | 잠재변수 생성 모델과 reparameterization trick | [신경망](../00_Foundations/05_neural-networks.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | Understanding deep learning requires rethinking generalization | Zhang et al., 2016 | [arXiv 1611.03530](https://arxiv.org/abs/1611.03530) | 신경망이 랜덤 라벨도 외운다 — 일반화에 대한 통념을 흔든 논문 | [신경망](../00_Foundations/05_neural-networks.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | Deep Double Descent: Where Bigger Models and More Data Hurt | Nakkiran et al., 2019 | [arXiv 1912.02292](https://arxiv.org/abs/1912.02292) | 편향-분산 트레이드오프의 현대적 수정 | [신경망](../00_Foundations/05_neural-networks.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |

---
링크 확인일: 2026-11-10 (arXiv API · Crossref · HTTP 응답으로 제목 대조)
