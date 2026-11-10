# 필독 자료 — NLP LLM

단어 임베딩 → 어텐션 → Transformer → 사전학습 → LLM 활용(RAG·에이전트·평가) 순으로 읽는다.

> **읽는 법:** ①→②→③ 순서. `선수 지식` 열의 링크를 먼저 훑고 오면 훨씬 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.

## ① 입문

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 블로그 | The Illustrated Transformer | Jay Alammar | [링크](https://jalammar.github.io/illustrated-transformer/) | Transformer 논문을 읽기 전 반드시 볼 그림 설명 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 영상 | Transformers, the tech behind LLMs | 3Blue1Brown | [링크](https://www.youtube.com/watch?v=wjZofJX0v4M) | GPT 내부를 시각적으로 설명 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 영상 | [1hr Talk] Intro to Large Language Models | Andrej Karpathy | [링크](https://www.youtube.com/watch?v=zjkBMFhNj_g) | LLM이 무엇이고 어디로 가는지 1시간 개관 | [신경망](../00_Foundations/05_neural-networks.md) |

## ② 핵심

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 영상 | Let's build GPT: from scratch, in code, spelled out. | Andrej Karpathy | [링크](https://www.youtube.com/watch?v=kCc8FmEb1nY) | GPT를 밑바닥부터 코딩. 논문 이해도가 크게 오른다 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 강의 | CS224N: NLP with Deep Learning | Stanford | [링크](https://web.stanford.edu/class/cs224n/) † | NLP 표준 강의 | [신경망](../00_Foundations/05_neural-networks.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 강의 | Hugging Face Learn (LLM Course 등) | Hugging Face | [링크](https://huggingface.co/learn) | transformers 라이브러리 실습 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | Efficient Estimation of Word Representations in Vector Space (Word2Vec) | Mikolov et al., 2013 | [arXiv 1301.3781](https://arxiv.org/abs/1301.3781) | 단어를 벡터로 — 임베딩의 출발점 | [선형대수](../00_Foundations/01_linear-algebra.md) · [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 논문 | Neural Machine Translation by Jointly Learning to Align and Translate | Bahdanau et al., 2014 | [arXiv 1409.0473](https://arxiv.org/abs/1409.0473) | 어텐션의 시작 | [신경망](../00_Foundations/05_neural-networks.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | Attention Is All You Need | Vaswani et al., 2017 | [arXiv 1706.03762](https://arxiv.org/abs/1706.03762) | Transformer. 현대 AI에서 가장 중요한 논문 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding | Devlin et al., 2018 | [arXiv 1810.04805](https://arxiv.org/abs/1810.04805) | 사전학습+파인튜닝 패러다임 (인코더) | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | Language Models are Few-Shot Learners (GPT-3) | Brown et al., 2020 | [arXiv 2005.14165](https://arxiv.org/abs/2005.14165) | 프롬프트만으로 과제를 푸는 in-context learning | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks (RAG) | Lewis et al., 2020 | [arXiv 2005.11401](https://arxiv.org/abs/2005.11401) | 검색 결합 생성 — 실무 LLM 서비스의 기본 구조 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |

## ③ 심화

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 논문 | Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks | Reimers & Gurevych, 2019 | [arXiv 1908.10084](https://arxiv.org/abs/1908.10084) | 문장 임베딩 — 검색·클러스터링·RAG의 기반 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 논문 | LoRA: Low-Rank Adaptation of Large Language Models | Hu et al., 2021 | [arXiv 2106.09685](https://arxiv.org/abs/2106.09685) | 저비용 파인튜닝의 표준 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 논문 | Chain-of-Thought Prompting Elicits Reasoning in Large Language Models | Wei et al., 2022 | [arXiv 2201.11903](https://arxiv.org/abs/2201.11903) | 단계적 추론 프롬프팅 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | ReAct: Synergizing Reasoning and Acting in Language Models | Yao et al., 2022 | [arXiv 2210.03629](https://arxiv.org/abs/2210.03629) | 추론+도구 사용 — LLM 에이전트의 기본 패턴 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | Training language models to follow instructions with human feedback (InstructGPT) | Ouyang et al., 2022 | [arXiv 2203.02155](https://arxiv.org/abs/2203.02155) | RLHF — ChatGPT류 모델의 정렬 방식 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | Scaling Laws for Neural Language Models | Kaplan et al., 2020 | [arXiv 2001.08361](https://arxiv.org/abs/2001.08361) | 모델·데이터·연산량과 성능의 관계 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ✅ | 논문 | BBQ: A Hand-Built Bias Benchmark for Question Answering | Parrish et al., 2022 | [arXiv 2110.08193](https://arxiv.org/abs/2110.08193) | LLM 편향 평가 벤치마크 — **정리 완료**: [노트](2026-11-03_bbq-bias-benchmark-qa) | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 블로그 | Lil'Log | Lilian Weng | [링크](https://lilianweng.github.io/) | 에이전트·프롬프팅·디퓨전 등 주제별 고품질 서베이 글 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |

† 표시는 이 환경에서 접속이 차단되어 자동 확인을 못 한 링크(널리 알려진 주소).

---
링크 확인일: 2026-11-10 (arXiv API · Crossref · HTTP 응답으로 제목 대조)
