# 필독 자료 — Computer Vision

CNN → 탐지/분할 → ViT → 멀티모달(CLIP) → 디퓨전 생성 모델.

> **읽는 법:** ①→②→③ 순서. **★** 는 먼저 읽을 코어 자료, **🆕** 는 2025~2026년에 나온 자료다.  
> `선수 지식`의 문서를 먼저 훑고 오면 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.  
> 읽기 가이드·실습 과제·기억 점검 퀴즈는 [PRACTICE.md](PRACTICE.md), 실습 노트북은 [LABS.md](../LABS.md).

**먼저 읽을 것 (★)**: ResNet → CLIP

## ① 입문

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 강의 | **[CS231n: Deep Learning for Computer Vision](https://cs231n.stanford.edu/)**<br>Stanford | CV 표준 강의. 강의노트가 특히 좋다 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 강의 | **[Hugging Face Diffusion Models Course](https://huggingface.co/learn/diffusion-course)**<br>Hugging Face | 디퓨전 모델을 노트북으로 직접 학습·샘플링 (무료) | [신경망](../00_Foundations/05_neural-networks.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 블로그 | **[What are Diffusion Models?](https://lilianweng.github.io/posts/2021-07-11-diffusion-models/)**<br>Lilian Weng, 2021 | DDPM 수식을 가장 친절하게 유도한 글 | [신경망](../00_Foundations/05_neural-networks.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |

## ② 핵심

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 논문 | **[ImageNet Classification with Deep Convolutional Neural Networks (AlexNet)](https://doi.org/10.1145/3065386)**<br>Krizhevsky et al., 2012 · DOI | 딥러닝 시대를 연 논문 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Very Deep Convolutional Networks for Large-Scale Image Recognition (VGG)](https://arxiv.org/abs/1409.1556)**<br>Simonyan & Zisserman, 2014 · arXiv 1409.1556 | 작은 필터를 깊게 쌓는 설계 | [신경망](../00_Foundations/05_neural-networks.md) |
| [✅](../03_Deep_Learning/2026-11-16_resnet-deep-residual-learning) | 논문 | ★ **[Deep Residual Learning for Image Recognition (ResNet)](https://arxiv.org/abs/1512.03385)**<br>He et al., 2015 · arXiv 1512.03385 | 잔차 연결로 100층 이상 학습 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[U-Net: Convolutional Networks for Biomedical Image Segmentation](https://arxiv.org/abs/1505.04597)**<br>Ronneberger et al., 2015 · arXiv 1505.04597 | 분할의 표준 구조. 디퓨전 모델의 뼈대로도 쓰임 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale (ViT)](https://arxiv.org/abs/2010.11929)**<br>Dosovitskiy et al., 2020 · arXiv 2010.11929 | 이미지에 Transformer 적용 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[End-to-End Object Detection with Transformers (DETR)](https://arxiv.org/abs/2005.12872)**<br>Carion et al., 2020 · arXiv 2005.12872 | 탐지를 집합 예측으로 바꾼 구조 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | ★ **[Learning Transferable Visual Models From Natural Language Supervision (CLIP)](https://arxiv.org/abs/2103.00020)**<br>Radford et al., 2021 · arXiv 2103.00020 | 이미지-텍스트 대조학습. 멀티모달 모델의 기반 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 논문 | **[Masked Autoencoders Are Scalable Vision Learners (MAE)](https://arxiv.org/abs/2111.06377)**<br>He et al., 2021 · arXiv 2111.06377 | 이미지의 75%를 가리고 복원하는 자기지도 학습 | [신경망](../00_Foundations/05_neural-networks.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[A ConvNet for the 2020s (ConvNeXt)](https://arxiv.org/abs/2201.03545)**<br>Liu et al., 2022 · arXiv 2201.03545 | ResNet을 한 단계씩 현대화하며 ViT와 비교 — ablation 읽기 연습에 최적 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Scalable Diffusion Models with Transformers (DiT)](https://arxiv.org/abs/2212.09748)**<br>Peebles & Xie, 2022 · arXiv 2212.09748 | U-Net 대신 Transformer를 쓴 디퓨전 — 최근 이미지·영상 생성의 기반 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[DINOv2: Learning Robust Visual Features without Supervision](https://arxiv.org/abs/2304.07193)**<br>Oquab et al., 2023 · arXiv 2304.07193 | 라벨 없이 학습한 범용 시각 특징 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Step-by-Step Diffusion: An Elementary Tutorial](https://arxiv.org/abs/2406.08929)**<br>Nakkiran et al., 2024 · arXiv 2406.08929 | 디퓨전·플로 매칭을 최소한의 수학으로 처음부터 설명 | [신경망](../00_Foundations/05_neural-networks.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |

## ③ 심화

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 논문 | **[Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks](https://arxiv.org/abs/1506.01497)**<br>Ren et al., 2015 · arXiv 1506.01497 | 2단계 객체 탐지의 표준 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[You Only Look Once: Unified, Real-Time Object Detection (YOLO)](https://arxiv.org/abs/1506.02640)**<br>Redmon et al., 2015 · arXiv 1506.02640 | 1단계 실시간 탐지 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Denoising Diffusion Probabilistic Models (DDPM)](https://arxiv.org/abs/2006.11239)**<br>Ho et al., 2020 · arXiv 2006.11239 | 디퓨전 생성 모델의 출발점 | [신경망](../00_Foundations/05_neural-networks.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[High-Resolution Image Synthesis with Latent Diffusion Models (Stable Diffusion)](https://arxiv.org/abs/2112.10752)**<br>Rombach et al., 2021 · arXiv 2112.10752 | 잠재공간 디퓨전 — 이미지 생성 대중화 | [신경망](../00_Foundations/05_neural-networks.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Flow Matching for Generative Modeling](https://arxiv.org/abs/2210.02747)**<br>Lipman et al., 2022 · arXiv 2210.02747 | 디퓨전의 뒤를 잇는 생성 모델 학습법 | [신경망](../00_Foundations/05_neural-networks.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Classifier-Free Diffusion Guidance](https://arxiv.org/abs/2207.12598)**<br>Ho & Salimans, 2022 · arXiv 2207.12598 | 프롬프트 반영 강도를 조절하는 guidance scale의 원리 | [신경망](../00_Foundations/05_neural-networks.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Segment Anything](https://arxiv.org/abs/2304.02643)**<br>Kirillov et al., 2023 · arXiv 2304.02643 | 분할 파운데이션 모델 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Visual Instruction Tuning (LLaVA)](https://arxiv.org/abs/2304.08485)**<br>Liu et al., 2023 · arXiv 2304.08485 | 이미지를 이해하는 LLM(VLM)의 기본 구조 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Sigmoid Loss for Language Image Pre-Training (SigLIP)](https://arxiv.org/abs/2303.15343)**<br>Zhai et al., 2023 · arXiv 2303.15343 | CLIP의 softmax를 sigmoid로 — 요즘 VLM의 이미지 인코더 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 논문 | **[SAM 2: Segment Anything in Images and Videos](https://arxiv.org/abs/2408.00714)**<br>Ravi et al., 2024 · arXiv 2408.00714 | 분할을 영상으로 확장 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Examining Gender and Racial Bias in Large Vision-Language Models Using a Novel Dataset of Parallel Images (PAIRS)](https://arxiv.org/abs/2402.05779)**<br>Fraser & Kiritchenko, 2024 · arXiv 2402.05779 | 성별·인종만 다른 이미지 쌍으로 VLM 편향 측정 (BBQ 노트의 멀티모달 확장) | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | 🆕 **[DINOv3](https://arxiv.org/abs/2508.10104)**<br>Siméoni et al., 2025 · arXiv 2508.10104 | 자기지도 시각 파운데이션 모델의 최신판 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[SAM 3: Segment Anything with Concepts](https://arxiv.org/abs/2511.16719)**<br>Meta, 2025 · arXiv 2511.16719 | 텍스트 개념으로 모든 해당 객체를 분할·추적 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[Qwen2.5-VL Technical Report](https://arxiv.org/abs/2502.13923)**<br>Alibaba, 2025 · arXiv 2502.13923 | 공개 가중치 VLM의 구조·학습 보고서 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[SmolVLM: Redefining small and efficient multimodal models](https://arxiv.org/abs/2504.05299)**<br>Marafioti et al., 2025 · arXiv 2504.05299 | 노트북에서도 도는 작은 VLM — 직접 뜯어보기 좋음 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |

---
링크 확인: 2026-11-10(기존 자료), 2026-11-16~17(추가 자료) — arXiv API · Crossref · HTTP 응답 · YouTube · GitHub로 제목 대조
