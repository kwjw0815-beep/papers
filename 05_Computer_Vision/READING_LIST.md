# 필독 자료 — Computer Vision

CNN → 탐지/분할 → ViT → 멀티모달(CLIP) → 디퓨전 생성 모델.

> **읽는 법:** ①→②→③ 순서. `선수 지식` 열의 링크를 먼저 훑고 오면 훨씬 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.

## ① 입문

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 강의 | CS231n: Deep Learning for Computer Vision | Stanford | [링크](https://cs231n.stanford.edu/) | CV 표준 강의. 강의노트가 특히 좋다 | [신경망](../00_Foundations/05_neural-networks.md) |

## ② 핵심

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 논문 | ImageNet Classification with Deep Convolutional Neural Networks (AlexNet) | Krizhevsky et al., 2012 | [DOI](https://doi.org/10.1145/3065386) | 딥러닝 시대를 연 논문 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | Very Deep Convolutional Networks for Large-Scale Image Recognition (VGG) | Simonyan & Zisserman, 2014 | [arXiv 1409.1556](https://arxiv.org/abs/1409.1556) | 작은 필터를 깊게 쌓는 설계 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | Deep Residual Learning for Image Recognition (ResNet) | He et al., 2015 | [arXiv 1512.03385](https://arxiv.org/abs/1512.03385) | 잔차 연결로 100층 이상 학습 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | U-Net: Convolutional Networks for Biomedical Image Segmentation | Ronneberger et al., 2015 | [arXiv 1505.04597](https://arxiv.org/abs/1505.04597) | 분할의 표준 구조. 디퓨전 모델의 뼈대로도 쓰임 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale (ViT) | Dosovitskiy et al., 2020 | [arXiv 2010.11929](https://arxiv.org/abs/2010.11929) | 이미지에 Transformer 적용 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | Learning Transferable Visual Models From Natural Language Supervision (CLIP) | Radford et al., 2021 | [arXiv 2103.00020](https://arxiv.org/abs/2103.00020) | 이미지-텍스트 대조학습. 멀티모달 모델의 기반 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |

## ③ 심화

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 논문 | Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks | Ren et al., 2015 | [arXiv 1506.01497](https://arxiv.org/abs/1506.01497) | 2단계 객체 탐지의 표준 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | You Only Look Once: Unified, Real-Time Object Detection (YOLO) | Redmon et al., 2015 | [arXiv 1506.02640](https://arxiv.org/abs/1506.02640) | 1단계 실시간 탐지 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | Denoising Diffusion Probabilistic Models (DDPM) | Ho et al., 2020 | [arXiv 2006.11239](https://arxiv.org/abs/2006.11239) | 디퓨전 생성 모델의 출발점 | [신경망](../00_Foundations/05_neural-networks.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | High-Resolution Image Synthesis with Latent Diffusion Models (Stable Diffusion) | Rombach et al., 2021 | [arXiv 2112.10752](https://arxiv.org/abs/2112.10752) | 잠재공간 디퓨전 — 이미지 생성 대중화 | [신경망](../00_Foundations/05_neural-networks.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | Segment Anything | Kirillov et al., 2023 | [arXiv 2304.02643](https://arxiv.org/abs/2304.02643) | 분할 파운데이션 모델 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | Visual Instruction Tuning (LLaVA) | Liu et al., 2023 | [arXiv 2304.08485](https://arxiv.org/abs/2304.08485) | 이미지를 이해하는 LLM(VLM)의 기본 구조 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |

---
링크 확인일: 2026-11-10 (arXiv API · Crossref · HTTP 응답으로 제목 대조)
