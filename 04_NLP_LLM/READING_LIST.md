# 필독 자료 — NLP LLM

단어 임베딩 → 어텐션 → Transformer → 사전학습 → LLM 활용(RAG·에이전트·평가) 순으로 읽는다.

> **읽는 법:** ①→②→③ 순서. **★** 는 먼저 읽을 코어 자료, **🆕** 는 2025~2026년에 나온 자료다.  
> `선수 지식`의 문서를 먼저 훑고 오면 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.

**먼저 읽을 것 (★)**: Attention Is All You Need → BERT → RAG → Adding Error Bars to Evals → BBQ

## ① 입문

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 영상 | **[Transformers, the tech behind LLMs](https://www.youtube.com/watch?v=wjZofJX0v4M)**<br>3Blue1Brown | GPT 내부를 시각적으로 설명 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 영상 | **[[1hr Talk] Intro to Large Language Models](https://www.youtube.com/watch?v=zjkBMFhNj_g)**<br>Andrej Karpathy | LLM이 무엇이고 어디로 가는지 1시간 개관 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 영상 | 🆕 **[Deep Dive into LLMs like ChatGPT](https://www.youtube.com/watch?v=7xTGNNLPyMI)**<br>Andrej Karpathy, 2025 · YouTube | 데이터 수집→토큰화→사전학습→후처리→추론을 3시간 반에 일반인 눈높이로 | [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 영상 | **[Attention in transformers, step-by-step](https://www.youtube.com/watch?v=eMlx5fFNoYc)**<br>3Blue1Brown · YouTube | Q·K·V가 실제로 무엇을 하는지 애니메이션으로 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 책 | **[Hands-On Large Language Models](https://github.com/HandsOnLLM/Hands-On-Large-Language-Models)**<br>Alammar & Grootendorst, 2024 · GitHub | 그림 중심 LLM 입문서 (전 장 Colab 노트북 공개) | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 블로그 | **[The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/)**<br>Jay Alammar | Transformer 논문을 읽기 전 반드시 볼 그림 설명 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |

## ② 핵심

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 영상 | **[Let's build GPT: from scratch, in code, spelled out.](https://www.youtube.com/watch?v=kCc8FmEb1nY)**<br>Andrej Karpathy | GPT를 밑바닥부터 코딩. 논문 이해도가 크게 오른다 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 영상 | **[Let's build the GPT Tokenizer](https://www.youtube.com/watch?v=zduSFxRajkE)**<br>Andrej Karpathy, 2024 · YouTube | BPE 토크나이저를 밑바닥부터 구현 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 영상 | **[Let's reproduce GPT-2 (124M)](https://www.youtube.com/watch?v=l8pRSuU81PU)**<br>Andrej Karpathy, 2024 · YouTube | GPT-2를 처음부터 재현 — 학습 속도·안정화 기법까지 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 강의 | **[CS224N: NLP with Deep Learning](https://web.stanford.edu/class/cs224n/)** †<br>Stanford | NLP 표준 강의 | [신경망](../00_Foundations/05_neural-networks.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 강의 | **[Hugging Face Learn (LLM Course 등)](https://huggingface.co/learn)**<br>Hugging Face | transformers 라이브러리 실습 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 강의 | 🆕 **[Stanford CS336: Language Modeling from Scratch](https://cs336.stanford.edu/)**<br>Stanford (Liang, Hashimoto) | 토크나이저·Transformer·학습·데이터·정렬을 과제로 직접 구현 (2026 봄 강의 영상 공개) | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 강의 | 🆕 **[Hugging Face Agents Course](https://huggingface.co/learn/agents-course)**<br>Hugging Face | 도구 사용·에이전트 프레임워크 실습 (무료) | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 책 | **[Build a Large Language Model (From Scratch)](https://github.com/rasbt/LLMs-from-scratch)**<br>Sebastian Raschka, 2024 · GitHub | GPT를 직접 구현·사전학습·미세조정하는 책 (코드 전체 공개) | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 책 | 🆕 **[AI Engineering](https://github.com/chiphuyen/aie-book)**<br>Chip Huyen, 2025 · GitHub | 파운데이션 모델로 제품을 만드는 전 과정: 평가·RAG·미세조정·추론 최적화 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 블로그 | **[Your AI Product Needs Evals](https://hamel.dev/blog/posts/evals/)**<br>Hamel Husain, 2024 | LLM 제품의 평가 체계를 단계별로 만드는 실전 글 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 블로그 | 🆕 **[Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)**<br>Anthropic, 2024 | 워크플로와 에이전트의 구분, 단순한 패턴부터 쓰라는 권고 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 블로그 | 🆕 **[Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)**<br>Anthropic, 2025 | 프롬프트 엔지니어링에서 컨텍스트 엔지니어링으로 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 문서 | **[What We Learned from a Year of Building with LLMs](https://applied-llms.org/)**<br>Yan, Bischof, Frye, Husain, Liu, Shankar, 2024 | LLM 응용의 전술·운영·전략 교훈 모음 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 문서 | 🆕 **[Model Context Protocol (MCP)](https://modelcontextprotocol.io/)**<br>Anthropic 외 | LLM과 도구·데이터를 연결하는 개방형 표준 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[Efficient Estimation of Word Representations in Vector Space (Word2Vec)](https://arxiv.org/abs/1301.3781)**<br>Mikolov et al., 2013 · arXiv 1301.3781 | 단어를 벡터로 — 임베딩의 출발점 | [선형대수](../00_Foundations/01_linear-algebra.md) · [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | **[Neural Machine Translation by Jointly Learning to Align and Translate](https://arxiv.org/abs/1409.0473)**<br>Bahdanau et al., 2014 · arXiv 1409.0473 | 어텐션의 시작 | [신경망](../00_Foundations/05_neural-networks.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Neural Machine Translation of Rare Words with Subword Units (BPE)](https://arxiv.org/abs/1508.07909)**<br>Sennrich et al., 2015 · arXiv 1508.07909 | 서브워드 토큰화의 원전 — 모든 LLM 토크나이저의 뿌리 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | ★ **[Attention Is All You Need](https://arxiv.org/abs/1706.03762)**<br>Vaswani et al., 2017 · arXiv 1706.03762 | Transformer. 현대 AI에서 가장 중요한 논문 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | ★ **[BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/abs/1810.04805)**<br>Devlin et al., 2018 · arXiv 1810.04805 | 사전학습+파인튜닝 패러다임 (인코더) | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Language Models are Few-Shot Learners (GPT-3)](https://arxiv.org/abs/2005.14165)**<br>Brown et al., 2020 · arXiv 2005.14165 | 프롬프트만으로 과제를 푸는 in-context learning | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | ★ **[Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks (RAG)](https://arxiv.org/abs/2005.11401)**<br>Lewis et al., 2020 · arXiv 2005.11401 | 검색 결합 생성 — 실무 LLM 서비스의 기본 구조 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Dense Passage Retrieval for Open-Domain Question Answering](https://arxiv.org/abs/2004.04906)**<br>Karpukhin et al., 2020 · arXiv 2004.04906 | 임베딩 기반 검색의 표준 — RAG의 "R" | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 논문 | **[Lost in the Middle: How Language Models Use Long Contexts](https://arxiv.org/abs/2307.03172)**<br>Liu et al., 2023 · arXiv 2307.03172 | 긴 문맥의 가운데 정보는 잘 못 쓴다 — RAG 설계에 직접 영향 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena](https://arxiv.org/abs/2306.05685)**<br>Zheng et al., 2023 · arXiv 2306.05685 | LLM으로 LLM을 채점할 때의 일치도와 편향 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | ★ 🆕 **[Adding Error Bars to Evals: A Statistical Approach to Language Model Evaluations](https://arxiv.org/abs/2411.00640)**<br>Miller (Anthropic), 2024 · arXiv 2411.00640 | LLM 평가 점수에 표준오차·신뢰구간을 붙이는 법 — 통계와 LLM 평가의 연결 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning](https://arxiv.org/abs/2501.12948)**<br>DeepSeek-AI, 2025 · arXiv 2501.12948 | 강화학습으로 추론(생각) 능력을 끌어낸 공개 가중치 모델 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |

## ③ 심화

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 블로그 | **[Lil'Log](https://lilianweng.github.io/)**<br>Lilian Weng | 에이전트·프롬프팅·디퓨전 등 주제별 고품질 서베이 글 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 블로그 | **[A Mathematical Framework for Transformer Circuits](https://transformer-circuits.pub/2021/framework/index.html)**<br>Elhage et al. (Anthropic), 2021 | Transformer를 회로로 분해해 이해하는 해석가능성의 출발점 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 블로그 | 🆕 **[On the Biology of a Large Language Model](https://transformer-circuits.pub/2025/attribution-graphs/biology.html)**<br>Anthropic, 2025 | 실제 LLM 내부에서 추론·계획이 일어나는 경로를 추적 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 블로그 | **[LLM Powered Autonomous Agents](https://lilianweng.github.io/posts/2023-06-23-agent/)**<br>Lilian Weng, 2023 | 계획·기억·도구 사용으로 에이전트를 정리한 글 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks](https://arxiv.org/abs/1908.10084)**<br>Reimers & Gurevych, 2019 · arXiv 1908.10084 | 문장 임베딩 — 검색·클러스터링·RAG의 기반 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 논문 | **[Scaling Laws for Neural Language Models](https://arxiv.org/abs/2001.08361)**<br>Kaplan et al., 2020 · arXiv 2001.08361 | 모델·데이터·연산량과 성능의 관계 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685)**<br>Hu et al., 2021 · arXiv 2106.09685 | 저비용 파인튜닝의 표준 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 논문 | **[RoFormer: Enhanced Transformer with Rotary Position Embedding (RoPE)](https://arxiv.org/abs/2104.09864)**<br>Su et al., 2021 · arXiv 2104.09864 | 요즘 LLM 대부분이 쓰는 위치 인코딩 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 논문 | **[KLUE: Korean Language Understanding Evaluation](https://arxiv.org/abs/2105.09680)**<br>Park et al., 2021 · arXiv 2105.09680 | 한국어 이해 평가의 기준 벤치마크 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Chain-of-Thought Prompting Elicits Reasoning in Large Language Models](https://arxiv.org/abs/2201.11903)**<br>Wei et al., 2022 · arXiv 2201.11903 | 단계적 추론 프롬프팅 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[ReAct: Synergizing Reasoning and Acting in Language Models](https://arxiv.org/abs/2210.03629)**<br>Yao et al., 2022 · arXiv 2210.03629 | 추론+도구 사용 — LLM 에이전트의 기본 패턴 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Training language models to follow instructions with human feedback (InstructGPT)](https://arxiv.org/abs/2203.02155)**<br>Ouyang et al., 2022 · arXiv 2203.02155 | RLHF — ChatGPT류 모델의 정렬 방식 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| [✅](2026-11-03_bbq-bias-benchmark-qa) | 논문 | ★ **[BBQ: A Hand-Built Bias Benchmark for Question Answering](https://arxiv.org/abs/2110.08193)**<br>Parrish et al., 2022 · arXiv 2110.08193 | LLM 편향 평가 벤치마크 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[MTEB: Massive Text Embedding Benchmark](https://arxiv.org/abs/2210.07316)**<br>Muennighoff et al., 2022 · arXiv 2210.07316 | 임베딩 모델을 고르는 기준이 되는 벤치마크 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 논문 | **[Holistic Evaluation of Language Models (HELM)](https://arxiv.org/abs/2211.09110)**<br>Liang et al., 2022 · arXiv 2211.09110 | 정확도뿐 아니라 편향·독성·효율까지 함께 보는 평가 틀 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Direct Preference Optimization: Your Language Model is Secretly a Reward Model](https://arxiv.org/abs/2305.18290)**<br>Rafailov et al., 2023 · arXiv 2305.18290 | RLHF를 단순한 분류 손실로 대체 — 요즘 후처리 학습의 표준 단계 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 논문 | **[QLoRA: Efficient Finetuning of Quantized LLMs](https://arxiv.org/abs/2305.14314)**<br>Dettmers et al., 2023 · arXiv 2305.14314 | 4비트 양자화 + LoRA로 GPU 한 장에서 미세조정 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 논문 | **[Retrieval-Augmented Generation for Large Language Models: A Survey](https://arxiv.org/abs/2312.10997)**<br>Gao et al., 2023 · arXiv 2312.10997 | Naive → Advanced → Modular RAG 흐름 정리 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[SWE-bench: Can Language Models Resolve Real-World GitHub Issues?](https://arxiv.org/abs/2310.06770)**<br>Jimenez et al., 2023 · arXiv 2310.06770 | 에이전트 코딩 능력의 대표 벤치마크 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[KoBBQ: Korean Bias Benchmark for Question Answering](https://arxiv.org/abs/2307.16778)**<br>Jin et al., 2023 · arXiv 2307.16778 | BBQ를 한국 문화에 맞게 옮긴 편향 벤치마크 (BBQ 노트와 함께) | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[The Llama 3 Herd of Models](https://arxiv.org/abs/2407.21783)**<br>Meta, 2024 · arXiv 2407.21783 | 대형 공개 가중치 모델의 데이터·학습·평가·안전 전 과정 보고서 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[From Local to Global: A Graph RAG Approach to Query-Focused Summarization](https://arxiv.org/abs/2404.16130)**<br>Edge et al., 2024 · arXiv 2404.16130 | 지식 그래프로 문서 전체를 요약·질의하는 GraphRAG | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[AI Agents That Matter](https://arxiv.org/abs/2407.01502)**<br>Kapoor et al., 2024 · arXiv 2407.01502 | 에이전트 평가의 함정: 비용 무시, 과적합, 재현 불가 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[The Prompt Report: A Systematic Survey of Prompt Engineering Techniques](https://arxiv.org/abs/2406.06608)**<br>Schulhoff et al., 2024 · arXiv 2406.06608 | 프롬프트 기법 용어·분류 총정리 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[Qwen3 Technical Report](https://arxiv.org/abs/2505.09388)**<br>Alibaba, 2025 · arXiv 2505.09388 | thinking/non-thinking 통합 모델 계열 보고서 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[gpt-oss-120b & gpt-oss-20b Model Card](https://arxiv.org/abs/2508.10925)**<br>OpenAI, 2025 · arXiv 2508.10925 | OpenAI의 공개 가중치 추론 모델 — 모델 카드 읽는 연습용 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[Measuring AI Ability to Complete Long Tasks](https://arxiv.org/abs/2503.14499)**<br>METR, 2025 · arXiv 2503.14499 | "사람이 걸리는 시간"으로 에이전트 능력을 재는 time horizon 지표 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | 🆕 **[Agentic Context Engineering: Evolving Contexts for Self-Improving Language Models](https://arxiv.org/abs/2510.04618)**<br>Zhang et al., 2025 · arXiv 2510.04618 | 가중치 대신 컨텍스트를 고쳐 가며 성능을 올리는 방법 (ICLR 2026) | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[Gemma 4 Technical Report](https://arxiv.org/abs/2607.02770)**<br>Google DeepMind, 2026 · arXiv 2607.02770 | 2026년 공개 가중치 모델 보고서 — 구조·학습·평가 서술 방식을 Llama 3·Qwen3 보고서와 비교 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[DeepSeek-V4: Towards Highly Efficient Million-Token Context Intelligence](https://arxiv.org/abs/2606.19348)**<br>DeepSeek-AI, 2026 · arXiv 2606.19348 | 2026년 대표 공개 가중치(MIT) 모델 — 100만 토큰 문맥을 위한 구조 선택 읽기 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |

† 표시는 이 환경에서 접속이 차단되어 자동 확인을 못 한 링크(널리 알려진 주소).

---
링크 확인: 2026-11-10(기존 자료), 2026-11-16~17(추가 자료) — arXiv API · Crossref · HTTP 응답 · YouTube · GitHub로 제목 대조
