# 필독 자료 — Deep Learning

신경망을 학습시키는 핵심 부품(역전파, 최적화, 정규화, 잔차연결)을 이해한다.

> **읽는 법:** ①→②→③ 순서. **★** 는 먼저 읽을 코어 자료, **🆕** 는 2025~2026년에 나온 자료다.  
> `선수 지식`의 문서를 먼저 훑고 오면 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.  
> 읽기 가이드·실습 과제·기억 점검 퀴즈는 [PRACTICE.md](PRACTICE.md), 실습 노트북은 [LABS.md](../LABS.md).

**먼저 읽을 것 (★)**: Adam → ResNet

## ① 입문

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 영상 | **[Neural Networks (시리즈)](https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi)**<br>3Blue1Brown | 신경망·경사하강·역전파를 시각적으로 설명 | [신경망](../00_Foundations/05_neural-networks.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 영상 | **[The spelled-out intro to neural networks and backpropagation: building micrograd](https://www.youtube.com/watch?v=VMj-3S1tku0)**<br>Andrej Karpathy | 역전파를 100줄 코드로 직접 구현 | [신경망](../00_Foundations/05_neural-networks.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 영상 | **[Neural Networks: Zero to Hero](https://karpathy.ai/zero-to-hero.html)**<br>Andrej Karpathy | micrograd → makemore → GPT까지 직접 코딩하는 연속 강의 | [신경망](../00_Foundations/05_neural-networks.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 강의 | **[Practical Deep Learning for Coders](https://course.fast.ai/)**<br>fast.ai | 코드부터 시작하는 top-down 방식 (무료) | [도구](../00_Foundations/08_data-tools.md) · [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 강의 | **[MIT 6.S191: Introduction to Deep Learning](https://introtodeeplearning.com/)**<br>MIT | 매년 갱신되는 딥러닝 입문 (영상·실습 무료) | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 책 | **[The Little Book of Deep Learning](https://fleuret.org/francois/lbdl.html)**<br>François Fleuret | 휴대폰 화면 크기로 쓴 150쪽 요약서 (PDF 무료) | [신경망](../00_Foundations/05_neural-networks.md) |

## ② 핵심

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 실습 | **[UvA Deep Learning Tutorials](https://uvadlc-notebooks.readthedocs.io/)**<br>Univ. of Amsterdam | 최적화·어텐션·생성 모델을 노트북으로 구현 (Colab) | [신경망](../00_Foundations/05_neural-networks.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 실습 | **[Annotated Deep Learning Paper Implementations](https://nn.labml.ai/)**<br>labml.ai | 논문 수식과 코드를 나란히 놓고 읽는 사이트 — 논문-코드 대응 연습에 최적 | [신경망](../00_Foundations/05_neural-networks.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 책 | **[Dive into Deep Learning](https://d2l.ai/)**<br>Zhang et al. | 수식·코드·설명이 함께 있는 무료 교재 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 책 | **[Understanding Deep Learning](https://udlbook.github.io/udlbook/)**<br>Simon Prince | 최신 내용까지 담은 그림 중심 교재 (PDF 무료) | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 책 | **[Deep Learning: Foundations and Concepts](https://www.bishopbook.com/)** †<br>Bishop & Bishop, 2024 | Transformer·디퓨전까지 담은 최신 교과서 (웹 무료 열람) | [선형대수](../00_Foundations/01_linear-algebra.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) · [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 블로그 | **[A Recipe for Training Neural Networks](https://karpathy.github.io/2019/04/25/recipe/)**<br>Andrej Karpathy, 2019 | 신경망 학습이 "조용히 실패"하는 이유와 단계별 점검 절차 | [신경망](../00_Foundations/05_neural-networks.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 문서 | **[Deep Learning Tuning Playbook](https://github.com/google-research/tuning_playbook)**<br>Google Research · GitHub | 학습률·배치 크기·옵티마이저를 체계적으로 튜닝하는 절차 | [신경망](../00_Foundations/05_neural-networks.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 논문 | **[Learning representations by back-propagating errors](https://doi.org/10.1038/323533a0)**<br>Rumelhart, Hinton, Williams, 1986 · DOI | 역전파의 원전 (3쪽) | [신경망](../00_Foundations/05_neural-networks.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 논문 | **[Dropout: A Simple Way to Prevent Neural Networks from Overfitting](https://jmlr.org/papers/v15/srivastava14a.html)**<br>Srivastava et al., 2014 | 가장 유명한 정규화 기법 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | ★ **[Adam: A Method for Stochastic Optimization](https://arxiv.org/abs/1412.6980)**<br>Kingma & Ba, 2014 · arXiv 1412.6980 | 기본 옵티마이저 | [미적분·최적화](../00_Foundations/02_calculus-optimization.md) · [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Deep learning](https://doi.org/10.1038/nature14539)**<br>LeCun, Bengio, Hinton, 2015 · DOI | 딥러닝 전체를 조망하는 Nature 리뷰 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift](https://arxiv.org/abs/1502.03167)**<br>Ioffe & Szegedy, 2015 · arXiv 1502.03167 | 깊은 망 학습 안정화 | [신경망](../00_Foundations/05_neural-networks.md) |
| [✅](2026-11-16_resnet-deep-residual-learning) | 논문 | ★ **[Deep Residual Learning for Image Recognition (ResNet)](https://arxiv.org/abs/1512.03385)**<br>He et al., 2015 · arXiv 1512.03385 | 잔차 연결 — Transformer까지 이어지는 핵심 아이디어 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Layer Normalization](https://arxiv.org/abs/1607.06450)**<br>Ba, Kiros, Hinton, 2016 · arXiv 1607.06450 | Transformer의 정규화 층. BatchNorm과의 차이 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Decoupled Weight Decay Regularization (AdamW)](https://arxiv.org/abs/1711.05101)**<br>Loshchilov & Hutter, 2017 · arXiv 1711.05101 | 요즘 거의 모든 모델이 쓰는 옵티마이저. Adam의 weight decay가 왜 틀렸는지 | [미적분·최적화](../00_Foundations/02_calculus-optimization.md) · [신경망](../00_Foundations/05_neural-networks.md) |

## ③ 심화

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 논문 | **[Long Short-Term Memory](https://doi.org/10.1162/neco.1997.9.8.1735)**<br>Hochreiter & Schmidhuber, 1997 · DOI | 순환신경망의 기울기 소실 해결 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Auto-Encoding Variational Bayes (VAE)](https://arxiv.org/abs/1312.6114)**<br>Kingma & Welling, 2013 · arXiv 1312.6114 | 잠재변수 생성 모델과 reparameterization trick | [신경망](../00_Foundations/05_neural-networks.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Generative Adversarial Networks](https://arxiv.org/abs/1406.2661)**<br>Goodfellow et al., 2014 · arXiv 1406.2661 | 생성 모델의 전환점 | [신경망](../00_Foundations/05_neural-networks.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Distilling the Knowledge in a Neural Network](https://arxiv.org/abs/1503.02531)**<br>Hinton, Vinyals, Dean, 2015 · arXiv 1503.02531 | 큰 모델의 지식을 작은 모델로 — 지식 증류 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Understanding deep learning requires rethinking generalization](https://arxiv.org/abs/1611.03530)**<br>Zhang et al., 2016 · arXiv 1611.03530 | 신경망이 랜덤 라벨도 외운다 — 일반화에 대한 통념을 흔든 논문 | [신경망](../00_Foundations/05_neural-networks.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[The Lottery Ticket Hypothesis: Finding Sparse, Trainable Neural Networks](https://arxiv.org/abs/1803.03635)**<br>Frankle & Carbin, 2018 · arXiv 1803.03635 | 큰 망 안에 "당첨된" 작은 부분망이 있다 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Deep Double Descent: Where Bigger Models and More Data Hurt](https://arxiv.org/abs/1912.02292)**<br>Nakkiran et al., 2019 · arXiv 1912.02292 | 편향-분산 트레이드오프의 현대적 수정 | [신경망](../00_Foundations/05_neural-networks.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Grokking: Generalization Beyond Overfitting on Small Algorithmic Datasets](https://arxiv.org/abs/2201.02177)**<br>Power et al., 2022 · arXiv 2201.02177 | 과적합 한참 뒤에 갑자기 일반화가 일어나는 현상 | [신경망](../00_Foundations/05_neural-networks.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Toy Models of Superposition](https://arxiv.org/abs/2209.10652)**<br>Elhage et al., 2022 · arXiv 2209.10652 | 뉴런 수보다 많은 특징을 겹쳐 저장하는 현상 — 해석가능성 연구의 기초 | [선형대수](../00_Foundations/01_linear-algebra.md) · [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Mamba: Linear-Time Sequence Modeling with Selective State Spaces](https://arxiv.org/abs/2312.00752)**<br>Gu & Dao, 2023 · arXiv 2312.00752 | 어텐션 없이 긴 시퀀스를 다루는 대안 구조 | [신경망](../00_Foundations/05_neural-networks.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |

† 표시는 이 환경에서 접속이 차단되어 자동 확인을 못 한 링크(널리 알려진 주소).

---
링크 확인: 2026-11-10(기존 자료), 2026-11-16~17(추가 자료) — arXiv API · Crossref · HTTP 응답 · YouTube · GitHub로 제목 대조
