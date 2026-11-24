# 필독 자료 — Open Models

학습 코드·데이터·가중치가 모두 공개된 모델을 "직접 돌려 보고 뜯어보며" 공부하기 위한 자료. 읽는 순서는 [02_study-method.md](02_study-method.md)를 따른다.

> **읽는 법:** 영어가 부담되면 바로 아래 **🇰🇷 한국어로 시작하기**부터 본다. 영어 자료는 ①→②→③ 순서. **★** 는 먼저 볼 코어 자료, **🆕** 는 2025~2026년에 나온 자료다.  
> `선수 지식`의 문서를 먼저 훑고 오면 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.  
> 읽기 가이드·실습 과제·기억 점검 퀴즈는 [PRACTICE.md](PRACTICE.md), 실습 노트북은 [LABS.md](../LABS.md).

## 🇰🇷 한국어로 시작하기

영어 자료가 막막하면 여기서 시작한다. **★** 표시가 한국어로 먼저 볼 자료다. 번역서는 아래 영어 표의 원서와 내용이 같고, 영어 표에서 한국어판이나 한국어 해설이 있는 자료에는 🇰🇷 링크를 달아 두었다.

| 유형 | 자료 | 왜 보나 |
|---|---|---|
| 논문·모델 | ★ 🆕 **[KORMo: Korean Open Reasoning Model for Everyone](https://arxiv.org/abs/2510.09426)**<br>KAIST 임경태 교수 연구팀 · 2025 · [모델](https://huggingface.co/KORMo-Team/KORMo-10B-sft) · [학습·추론 코드](https://github.com/MLP-Lab/KORMo-tutorial) · [한국어 소개 기사](https://www.oss.kr/pages/11/357) | 학습 데이터·코드·중간 모델까지 공개한 한국어·영어 10.8B 모델. 연구팀은 "비영어권 최초의 완전 오픈소스 LLM"이라고 밝힌다 |
| 영상 | ★ 🆕 **[모두를 위한 Full stack 오픈소스 언어모델 KORMo 개발일지](https://www.youtube.com/watch?v=yvLlNHFcT-Y)**<br>인공지능팩토리 AIF 세미나 · 2025 · [세미나 페이지](https://aifactory.space/ko/task/9234/overview) | 완전 공개 모델을 만드는 과정을 한국어로 듣는다 |
| 책·강의 | ★ 🆕 **[밑바닥부터 만들면서 배우는 LLM](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=372272431)**<br>세바스찬 라시카 · 박해선 옮김 · 길벗 · 2025 · [역자 강의](https://www.youtube.com/playlist?list=PLJN246lAkhQhgakhcxz-5GwG_NYuJgSv1) · [코드](https://github.com/rickiepark/llm-from-scratch) | GPT를 직접 구현·사전학습·미세조정 — 이 트랙의 lab02와 같은 흐름을 책으로 |
| 책 | 🆕 **[밑바닥부터 시작하는 딥러닝 6](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=400884754)**<br>사이토 고키 · 개앞맵시 옮김 · 한빛미디어 · 2026 | 일본어 원서 소개에 따르면 주제는 LLM: 토크나이저부터 Transformer, 사전학습·후처리를 직접 구현 |
| 영상 | **[LLM 바닥부터 만들기 #1 사전학습](https://www.youtube.com/watch?v=osv2csoHVAo)**<br>홍정모 | 사전학습 과정을 한 시간에 정리 |
| 블로그 | 🆕 **[Kanana-2 개발기 (1) 사전학습 · (2) 후처리](https://tech.kakao.com/posts/807)**<br>카카오 · 2026 · [(2) post-training](https://tech.kakao.com/posts/808) · [공개 보도자료](https://www.kakaocorp.com/page/detail/11854) | 가중치 공개 모델을 만든 회사가 직접 쓴 학습 결정 기록 (한국어) |
| 논문(영어) | 🆕 **[독자 AI 파운데이션 모델 기술 보고서: K-EXAONE · Solar Open · A.X K1](https://arxiv.org/abs/2601.01739)**<br>LG AI연구원 · 업스테이지 · SK텔레콤 · 2026 · [K-EXAONE 2.0](https://arxiv.org/abs/2608.04505) · [Solar Open](https://arxiv.org/abs/2601.07022) · [Solar Open 2](https://arxiv.org/abs/2607.20062) · [A.X K1](https://arxiv.org/abs/2601.09200) | 정부 프로젝트로 만든 한국 대표 가중치 공개 모델들. KORMo(완전 공개)와 공개 범위를 비교해 보기 |
| 논문(영어) | 🆕 **[EXAONE 4.0 · Kanana · HyperCLOVA X THINK](https://arxiv.org/abs/2507.11407)**<br>LG AI연구원 · 카카오 · 네이버 · 2025 · [Kanana](https://arxiv.org/abs/2502.18934) · [HyperCLOVA X THINK](https://arxiv.org/abs/2506.22403) | 한국 기업 모델의 기술 보고서 |

> `논문(영어)`는 영어로 쓰였지만 한국어·한국 모델을 다루는 논문이다.

## 🌐 영어 자료

**먼저 읽을 것 (★)**: nanoGPT → Pythia → nanochat → Olmo 3

## ① 입문

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 영상 | 🆕 **[Deep Dive into LLMs like ChatGPT](https://www.youtube.com/watch?v=7xTGNNLPyMI)**<br>Andrej Karpathy, 2025 · YouTube | LLM 한 개가 만들어지는 전 과정을 먼저 큰 그림으로 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 책 | **[Build a Large Language Model (From Scratch)](https://github.com/rasbt/LLMs-from-scratch)**<br>Sebastian Raschka, 2024 · GitHub<br>🇰🇷 [한국어판](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=372272431) | GPT 구현→사전학습→공개 가중치 불러오기→미세조정을 장별 노트북으로 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
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
링크 확인: 2026-11-10(기존 자료), 2026-11-16~17(추가 자료), 2026-11-23~24(한국어 자료) — arXiv API · Crossref · HTTP 응답 · YouTube · GitHub로 제목 대조
