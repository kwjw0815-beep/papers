# 추천 자료 — ResNet과 잔차 연결

> 링크는 2026-11-17에 arXiv API·HTTP 응답으로 존재와 제목을 확인했다.

| 우선순위 | 유형 | 제목 | 저자/출처 | 링크 | 추천 이유 |
|---|---|---|---|---|---|
| ⭐⭐⭐ | 논문 | Identity Mappings in Deep Residual Networks | He et al., 2016 | [arXiv 1603.05027](https://arxiv.org/abs/1603.05027) | 같은 저자의 후속작. 지름길이 "순수한 항등"일 때 신호가 블록 사이를 직접 오간다는 것을 식으로 보이고 pre-activation 블록을 제안 |
| ⭐⭐⭐ | 논문 | Batch Normalization | Ioffe & Szegedy, 2015 | [arXiv 1502.03167](https://arxiv.org/abs/1502.03167) | ResNet이 전제로 쓰는 부품. "수렴은 시작되는데 깊으면 나빠진다"는 문제 설정을 이해하려면 필요 |
| ⭐⭐ | 논문 | Highway Networks | Srivastava et al., 2015 | [arXiv 1505.00387](https://arxiv.org/abs/1505.00387) | 게이트가 달린 지름길. ResNet의 Related Work가 무엇과 자신을 구별하는지 직접 비교 |
| ⭐⭐ | 논문 | Visualizing the Loss Landscape of Neural Nets | Li et al., 2017 | [arXiv 1712.09913](https://arxiv.org/abs/1712.09913) | 지름길이 있으면 손실 지형이 얼마나 매끄러워지는지 그림으로 보여 줌 — "왜 쉬워지는가"에 대한 시각적 설명 |
| ⭐⭐ | 논문 | Residual Networks Behave Like Ensembles of Relatively Shallow Networks | Veit et al., 2016 | [arXiv 1605.06431](https://arxiv.org/abs/1605.06431) | ResNet을 길이가 다른 여러 경로의 모음으로 해석. 학습 중 기울기는 주로 짧은 경로에서 온다는 관찰 |
| ⭐⭐ | 논문 | ResNet strikes back: An improved training procedure in timm | Wightman et al., 2021 | [arXiv 2110.00476](https://arxiv.org/abs/2110.00476) | 구조는 그대로 두고 학습 절차만 바꿔 ResNet-50의 정확도를 크게 올림 — "구조 vs 학습 레시피"를 구분하는 눈 |
| ⭐ | 논문 | A ConvNet for the 2020s (ConvNeXt) | Liu et al., 2022 | [arXiv 2201.03545](https://arxiv.org/abs/2201.03545) | ResNet을 한 단계씩 현대화하는 ablation의 교과서 |
| ⭐ | 논문 | Densely Connected Convolutional Networks (DenseNet) | Huang et al., 2016 | [arXiv 1608.06993](https://arxiv.org/abs/1608.06993) | 더하기 대신 이어 붙이기(concatenation)로 지름길을 만든 변형 |
| ⭐ | 코드 | torchvision ResNet | PyTorch | [문서](https://docs.pytorch.org/vision/stable/models/resnet.html) | 논문의 Table 1을 코드(`BasicBlock`, `Bottleneck`)와 한 줄씩 대조해 보기 |
| ⭐ | 실습 | Lab 02 · 학습 동역학 | 이 저장소 | [노트북](../labs/lab02_training_dynamics.ipynb) | degradation 현상과 잔차 연결의 효과를 CPU 1분 안에 재현 |

## 학습 순서 제안
1. (입문) 이 노트의 Figure 설명을 보며 논문의 Figure 1 → 2 → 4를 직접 확인
2. (실습) Lab 02의 3절 실행 → "직접 해보기 3"으로 깊이를 바꿔 보기
3. (심화) *Identity Mappings* 로 "왜"에 대한 수식 설명 → *Loss Landscape* 로 그림 설명
4. (비판적 읽기) *ResNet strikes back* 을 읽고, 논문 표의 숫자를 다른 논문과 비교할 때 무엇을 확인해야 하는지 정리
