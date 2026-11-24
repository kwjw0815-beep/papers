# 추천 자료 — LLaVA와 VLM 구조

> 모든 arXiv 링크는 2026-11-24에 arXiv API로 존재와 제목을 확인했다. GitHub 링크는 응답 코드(200)로 확인했다.

| 우선순위 | 유형 | 제목 | 저자/출처 | 링크 | 추천 이유 |
|---|---|---|---|---|---|
| ⭐⭐⭐ | 논문 | Improved Baselines with Visual Instruction Tuning (LLaVA-1.5) | Liu et al., CVPR 2024 | [arXiv 2310.03744](https://arxiv.org/abs/2310.03744) | MLP 연결층, 336px 입력, **응답 형식 프롬프트**. 객관식 "선택지 문자로 답하라"와 정보 부족 시 "Unanswerable" 지시(11.1% → 67.8%)가 챌린지 Step 2~3에 바로 쓰인다 |
| ⭐⭐⭐ | 논문 | Qwen2.5-VL Technical Report | Bai et al., 2025 | [arXiv 2502.13923](https://arxiv.org/abs/2502.13923) | 챌린지 Step 2 베이스라인 후보. 같은 골격에 **동적 해상도**(이미지 크기에 따라 시각 토큰 수가 변함)를 더한 최신 VLM |
| ⭐⭐⭐ | 논문 | Learning Transferable Visual Models From Natural Language Supervision (CLIP) | Radford et al., ICML 2021 | [arXiv 2103.00020](https://arxiv.org/abs/2103.00020) | LLaVA의 비전 인코더. 인터넷 이미지-텍스트 4억 쌍으로 학습했다. LLaVA 저자가 지목한 **편향의 한 출처**이고, 논문 7.1절(Bias)에 직접 분석이 있다 |
| ⭐⭐ | 논문 | An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale (ViT) | Dosovitskiy et al., ICLR 2021 | [arXiv 2010.11929](https://arxiv.org/abs/2010.11929) | 이미지를 패치로 잘라 토큰처럼 다루는 아이디어의 원조. "시각 토큰"의 기초 |
| ⭐⭐ | 논문 | BLIP-2: Bootstrapping Language-Image Pre-training with Frozen Image Encoders and Large Language Models | Li et al., ICML 2023 | [arXiv 2301.12597](https://arxiv.org/abs/2301.12597) | LLaVA가 비교한 대안 연결 방식 **Q-Former**. 고정된 인코더와 LLM을 잇는 다른 설계 |
| ⭐⭐ | 논문 | Evaluating Object Hallucination in Large Vision-Language Models (POPE) | Li et al., EMNLP 2023 | [arXiv 2305.10355](https://arxiv.org/abs/2305.10355) | 이미지에 없는 물체를 "있다"고 하는 환각을 측정한다. 지시 데이터에 자주 나오거나 함께 나오는 물체일수록 환각이 잦다. "함께 자주 나오는 집단과 속성"이라는 고정관념과 구조가 비슷하다 (추측) |
| ⭐ | 논문 | Flamingo: a Visual Language Model for Few-Shot Learning | Alayrac et al., NeurIPS 2022 | [arXiv 2204.14198](https://arxiv.org/abs/2204.14198) | gated cross-attention으로 잇는 방식. LLaVA가 "멀티모달의 GPT-3 순간"이라 부른 이전 세대 대표 모델 |
| ⭐ | 논문 | Self-Instruct: Aligning Language Models with Self-Generated Instructions | Wang et al., ACL 2023 | [arXiv 2212.10560](https://arxiv.org/abs/2212.10560) | LLM으로 지시 데이터를 만드는 텍스트 쪽 선행 연구 (LLaVA 참고문헌) |
| ⭐ | 논문 | LLaVA-OneVision: Easy Visual Task Transfer | Li et al., 2024 | [arXiv 2408.03326](https://arxiv.org/abs/2408.03326) | LLaVA 계열의 이후 발전. 단일 이미지·다중 이미지·비디오를 한 모델로 다룬다 |
| ⭐ | 코드 | LLaVA GitHub | Haotian Liu | [github.com/haotian-liu/LLaVA](https://github.com/haotian-liu/LLaVA) | 학습·추론 코드, 데이터 생성 프롬프트, 체크포인트 |

## 학습 순서 제안
1. (입문) **ViT** → **CLIP**: 이미지가 어떻게 패치를 거쳐 임베딩이 되는지
2. (본론) **LLaVA** → **LLaVA-1.5**: 연결층, 2단계 학습, 응답 형식 프롬프트
3. (대회 실전) **Qwen2.5-VL**: Step 2 베이스라인의 입력 형식과 동적 해상도
4. (편향·신뢰성) **POPE**(환각) → BBQ 정리의 [references.md](../2026-11-03_bbq-bias-benchmark-qa/references.md)에 있는 **PAIRS**, **BBQ-V**(멀티모달 편향 측정)
5. (실습) [챌린지 저장소](https://github.com/kwjw0815-beep/multimodal-ai-bias-challenge) Step 2에서 VLM을 직접 돌려 시각 토큰 수와 응답 형식 프롬프트의 효과를 확인
