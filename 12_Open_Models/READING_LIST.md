# 필독 자료 — Open Models

학습 코드·데이터·가중치가 모두 공개된 모델을 "직접 돌려 보고 뜯어보며" 공부하기 위한 자료. 읽는 순서는 [02_study-method.md](02_study-method.md)를 따른다.

> **읽는 법:** ①→②→③ 순서. **★** 는 먼저 읽을 코어 자료, **🆕** 는 2025~2026년에 나온 자료다.  
> `선수 지식`의 문서를 먼저 훑고 오면 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.  
> 읽기 가이드·실습 과제·기억 점검 퀴즈는 [PRACTICE.md](PRACTICE.md), 실습 노트북은 [LABS.md](../LABS.md).

**먼저 읽을 것 (★)**: nanoGPT → Pythia → nanochat → Olmo 3

## ① 입문

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 영상 | 🆕 **[Deep Dive into LLMs like ChatGPT](https://www.youtube.com/watch?v=7xTGNNLPyMI)**<br>Andrej Karpathy, 2025 · YouTube | LLM 한 개가 만들어지는 전 과정을 먼저 큰 그림으로 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 책 | **[Build a Large Language Model (From Scratch)](https://github.com/rasbt/LLMs-from-scratch)**<br>Sebastian Raschka, 2024 · GitHub | GPT 구현→사전학습→공개 가중치 불러오기→미세조정을 장별 노트북으로 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 저장소 | ★ **[nanoGPT](https://github.com/karpathy/nanoGPT)**<br>Andrej Karpathy · GitHub | 약 300줄 모델 + 300줄 학습 루프. 셰익스피어 글자 모델은 노트북 CPU로도 학습 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[TinyStories: How Small Can Language Models Be and Still Speak Coherent English?](https://arxiv.org/abs/2305.07759)**<br>Eldan & Li, 2023 · arXiv 2305.07759 | 수백만 파라미터로도 말이 되는 이야기를 쓰게 하는 데이터셋 — 작은 실험의 표준 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |

## ② 핵심

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 저장소 | ★ 🆕 **[nanochat](https://github.com/karpathy/nanochat)**<br>Andrej Karpathy, 2025~ · GitHub | 토크나이저→사전학습→SFT→RL→평가→채팅 UI까지 한 저장소. GPT-2급을 약 2시간(8×H100)에 학습 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 모델 | 🆕 **[SmolLM3-3B](https://huggingface.co/HuggingFaceTB/SmolLM3-3B)**<br>Hugging Face, 2025 | 가중치 + 데이터 구성 + 학습 설정을 공개한 3B 모델 (모델 카드가 좋은 읽기 자료) | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 도구 | **[lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness)**<br>EleutherAI · GitHub | 논문의 평가 숫자를 재현할 때 쓰는 표준 도구 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | ★ **[Pythia: A Suite for Analyzing Large Language Models Across Training and Scaling](https://arxiv.org/abs/2304.01373)**<br>Biderman et al. (EleutherAI), 2023 · arXiv 2304.01373 | 70M~12B 8개 크기 × 154개 체크포인트, 데이터·순서까지 공개 — "학습 과정"을 관찰하는 용도 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[2 OLMo 2 Furious](https://arxiv.org/abs/2501.00656)**<br>Walsh et al. (Ai2), 2024 · arXiv 2501.00656 | 데이터·코드·가중치·로그를 모두 공개한 7B/13B 모델과 학습 안정화 기법 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 논문 | 🆕 **[SmolLM2: When Smol Goes Big — Data-Centric Training of a Small Language Model](https://arxiv.org/abs/2502.02737)**<br>Allal et al. (Hugging Face), 2025 · arXiv 2502.02737 | 135M~1.7B 소형 모델의 데이터 구성·학습 단계 공개 (중간 체크포인트 포함) | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | ★ 🆕 **[Olmo 3](https://arxiv.org/abs/2512.13961)**<br>Ai2, 2025 · arXiv 2512.13961 | "모델 흐름(model flow)" 전체 공개: 사전학습→중간학습→긴 문맥→SFT→DPO→RLVR | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |

## ③ 심화

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 문서 | **[The Open Source AI Definition 1.0](https://opensource.org/ai/open-source-ai-definition)**<br>Open Source Initiative, 2024 | "오픈소스 AI"의 공식 정의 — 가중치만 공개는 해당하지 않는 이유 | - |
| ⬜ | 저장소 | 🆕 **[Marin](https://github.com/marin-community/marin)**<br>Stanford 외 (Open Athena) · GitHub | 실험·실패까지 공개 기록하는 "오픈 개발" 방식의 파운데이션 모델 연구 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 저장소 | 🆕 **[modded-nanogpt](https://github.com/KellerJordan/modded-nanogpt)**<br>Keller Jordan · GitHub | GPT-2 small 학습 속도 기록 경쟁 — 최적화 기법이 하나씩 쌓인 기록 | [미적분·최적화](../00_Foundations/02_calculus-optimization.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 저장소 | 🆕 **[autoresearch](https://github.com/karpathy/autoresearch)**<br>Andrej Karpathy, 2026 · GitHub | AI 에이전트가 학습 코드를 고치고 5분 실험을 반복 — 공개 학습 코드가 있어야 가능한 연구 방식 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[Reproducible scaling laws for contrastive language-image learning (OpenCLIP)](https://arxiv.org/abs/2212.07143)**<br>Cherti et al., 2022 · arXiv 2212.07143 | CLIP을 공개 데이터(LAION)·공개 코드로 재현 — 비전 쪽 완전 공개 사례 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[LLM360: Towards Fully Transparent Open-Source LLMs](https://arxiv.org/abs/2312.06550)**<br>Liu et al., 2023 · arXiv 2312.06550 | 학습 코드·데이터·중간 체크포인트·분석까지 공개하자는 제안과 사례(Amber, CrystalCoder) | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Opening up ChatGPT: Tracking openness, transparency, and accountability in instruction-tuned text generators](https://arxiv.org/abs/2307.05532)**<br>Liesenfeld et al., 2023 · arXiv 2307.05532 | "오픈"이라는 이름의 모델들을 항목별로 점검 — open-washing 문제 | - |
| ⬜ | 논문 | **[Dolma: an Open Corpus of Three Trillion Tokens for Language Model Pretraining Research](https://arxiv.org/abs/2402.00159)**<br>Soldaini et al. (Ai2), 2024 · arXiv 2402.00159 | 사전학습 데이터를 어떻게 모으고 거르는지 — 데이터 큐레이션 도구까지 공개 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[OLMo: Accelerating the Science of Language Models](https://arxiv.org/abs/2402.00838)**<br>Groeneveld et al. (Ai2), 2024 · arXiv 2402.00838 | 완전 공개 LLM의 취지와 첫 모델 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[The Model Openness Framework: Promoting Completeness and Openness for Reproducibility, Transparency, and Usability in Artificial Intelligence](https://arxiv.org/abs/2403.13784)**<br>White et al. (Linux Foundation), 2024 · arXiv 2403.13784 | 공개 수준을 구성요소별로 등급화하는 틀 | - |
| ⬜ | 논문 | **[Chronos: Learning the Language of Time Series](https://arxiv.org/abs/2403.07815)**<br>Ansari et al. (Amazon), 2024 · arXiv 2403.07815 | 코드·가중치·데이터셋을 공개한 시계열 파운데이션 모델 — 언어모델이 아닌 분야의 사례 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | 🆕 **[Apertus: Democratizing Open and Compliant LLMs for Global Language Environments](https://arxiv.org/abs/2509.14233)**<br>Swiss AI Initiative, 2025 · arXiv 2509.14233 | 데이터 규정 준수와 다국어를 내세운 완전 공개 8B/70B 모델 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[Muon is Scalable for LLM Training](https://arxiv.org/abs/2502.16982)**<br>Liu et al. (Moonshot), 2025 · arXiv 2502.16982 | nanochat·modded-nanogpt가 쓰는 Muon 옵티마이저의 대규모 검증 | [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |

---
링크 확인: 2026-11-10(기존 자료), 2026-11-16~17(추가 자료) — arXiv API · Crossref · HTTP 응답 · YouTube · GitHub로 제목 대조
