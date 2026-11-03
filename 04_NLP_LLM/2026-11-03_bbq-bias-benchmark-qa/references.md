# 추천 자료 — BBQ와 (멀티모달) 편향 평가

> 모든 링크는 2026-11-03에 arXiv API로 존재와 제목을 확인했다.

| 우선순위 | 유형 | 제목 | 저자/출처 | 링크 | 추천 이유 |
|---|---|---|---|---|---|
| ⭐⭐⭐ | 논문 | BBQ-V: Benchmarking Visual Stereotype Bias in Large Multimodal Models | 2025 | [arXiv 2502.08779](https://arxiv.org/abs/2502.08779) | BBQ를 **실제 이미지·다인물 이미지**로 확장 (9범주, 14,144 이미지-질문 쌍). 멀티모달 챌린지와 가장 직접적으로 연결됨 |
| ⭐⭐⭐ | 논문 | Examining Gender and Racial Bias in Large Vision-Language Models Using a Novel Dataset of Parallel Images (PAIRS) | Fraser & Kiritchenko, 2024 | [arXiv 2402.05779](https://arxiv.org/abs/2402.05779) | 배경은 같고 **성별·인종만 다른 생성 이미지 쌍**으로 VLM 편향을 측정. BBQ의 "한 변수만 바꾸기"를 이미지에 적용한 사례 |
| ⭐⭐⭐ | 논문 | KoBBQ: Korean Bias Benchmark for Question Answering | Jin et al., TACL 2024 | [arXiv 2307.16778](https://arxiv.org/abs/2307.16778) | BBQ를 한국 문화에 맞게 옮기는 프레임워크 (그대로 이전 / 대상 수정 / 제거). "편향은 문화 의존적"이라는 BBQ 한계에 대한 직접적 답 |
| ⭐⭐ | 논문 | UnQovering Stereotyping Biases via Underspecified Questions | Li et al., Findings of EMNLP 2020 | [arXiv 2010.02428](https://arxiv.org/abs/2010.02428) | BBQ의 직접적 선행 연구. **likelihood 기반** 측정과 BBQ의 **출력 기반** 측정 비교용 |
| ⭐⭐ | 논문 | VLBiasBench: A Comprehensive Benchmark for Evaluating Bias in Large Vision-Language Model | 2024 | [arXiv 2406.14194](https://arxiv.org/abs/2406.14194) | BBQ와 같은 9범주 + 교차 2범주를 SDXL 생성 이미지 46,848장으로 구성. 개방형/폐쇄형 질문 모두 포함 |
| ⭐⭐ | 논문 | Language (Technology) is Power: A Critical Survey of "Bias" in NLP | Blodgett et al., ACL 2020 | [arXiv 2005.14050](https://arxiv.org/abs/2005.14050) | BBQ가 편향 정의의 출발점으로 삼은 서베이. "bias를 측정한다"는 말이 얼마나 모호한지 이해하기 |
| ⭐ | 논문 | On Measures of Biases and Harms in NLP | Dev et al., 2021 | [arXiv 2108.03362](https://arxiv.org/abs/2108.03362) | BBQ 본문에 "What do bias measures measure?"(구 제목)로 인용됨. 편향 지표와 실제 해(harm)의 연결 |
| ⭐ | 논문 | Visual Instruction Tuning (LLaVA) | Liu et al., NeurIPS 2023 | [arXiv 2304.08485](https://arxiv.org/abs/2304.08485) | 멀티모달 편향을 이해하기 전 **VLM이 어떻게 생겼는지** 기초 |
| ⭐ | 데이터 | BBQ GitHub | NYU MLL | [github.com/nyu-mll/BBQ](https://github.com/nyu-mll/BBQ) | 데이터·템플릿·분석 코드 (CC-BY 4.0) |

## 학습 순서 제안
1. (입문) **BBQ** 본 논문 → Blodgett et al. (2020)으로 "편향" 정의의 다양성 이해
2. (심화) **UnQover**와 비교: likelihood vs 출력 측정의 장단점 → **KoBBQ**로 문화 적응 문제
3. (멀티모달) **LLaVA**로 VLM 구조 → **PAIRS**(통제된 이미지 쌍) → **BBQ-V / VLBiasBench**(BBQ의 멀티모달 확장)
4. (실습) BBQ 데이터에 bias score를 직접 구현하고, VLM에 이미지 유무를 바꿔 가며 점수 변화 관찰 ([챌린지 저장소](https://github.com/kwjw0815-beep/multimodal-ai-bias-challenge))
