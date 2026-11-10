# 어텐션·Transformer

## 왜 필요한가
2017년 이후 NLP는 물론 비전(ViT), 추천(SASRec), 시계열(TFT), 멀티모달(CLIP, LLaVA)까지 거의 모든 논문이 Transformer 위에 있다. 이 문서의 내용을 알면 `04_NLP_LLM`의 대부분을 읽을 수 있다.

## 최소한 이것만
| 개념 | 직관 | 정의 |
|---|---|---|
| 토큰 (token) | 모델이 다루는 텍스트 조각 (단어보다 작을 수 있음) | BPE/WordPiece 등 subword 토크나이저 |
| 임베딩 (embedding) | 토큰을 의미를 담은 벡터로 | 학습되는 조회 테이블 $E\in\mathbb{R}^{V\times d}$ |
| 어텐션 (attention) | 지금 위치를 이해하기 위해 **다른 위치들을 얼마나 참고할지** 가중치를 계산해 섞음 | 가중 평균 |
| Self-attention | 한 문장 안에서 토큰끼리 서로 참조 | Q, K, V가 모두 같은 입력에서 나옴 |
| 위치 인코딩 (positional encoding) | 어텐션은 순서를 모르므로 위치 정보를 더해 줌 | sinusoidal, learned, RoPE … |
| 컨텍스트 길이 | 한 번에 볼 수 있는 토큰 수 | context window |

## 어텐션 수식 뜯어보기
$$\text{Attention}(Q,K,V)=\text{softmax}\!\left(\frac{QK^\top}{\sqrt{d_k}}\right)V$$

1. 각 토큰이 세 가지 벡터를 만든다: **Query**(내가 찾는 것), **Key**(내가 가진 것의 색인), **Value**(실제 전달할 내용).
2. $QK^\top$: 모든 질의-키 쌍의 **내적** = 관련도 점수 표 (n×n). → [선형대수](01_linear-algebra.md)
3. $\sqrt{d_k}$로 나눔: 차원이 크면 내적이 커져 softmax가 한쪽으로 쏠리는 것을 방지.
4. softmax: 각 행을 합이 1인 가중치로.
5. 그 가중치로 Value들을 가중 평균 → 문맥이 반영된 새 표현.

- **Multi-head:** 위 과정을 여러 개(head) 병렬로 → 문법적 관계, 지시 관계 등 서로 다른 관계를 동시에 포착.
- **계산량:** 모든 쌍을 보므로 길이 n에 대해 $O(n^2)$. 긴 문맥이 비싼 이유.

## Transformer 블록
```
입력 임베딩 + 위치 인코딩
  └─ [ Multi-Head Self-Attention → Add & Norm → Feed-Forward(MLP) → Add & Norm ] × N층
```
`Add`는 잔차 연결, `Norm`은 Layer Normalization → [신경망](05_neural-networks.md)

| 계열 | 구조 | 학습 목표 | 대표 | 용도 |
|---|---|---|---|---|
| 인코더 | 양방향 어텐션 | 가린 토큰 맞히기 (MLM) | BERT, Sentence-BERT | 분류, 임베딩, 검색 |
| 디코더 | 왼쪽만 보는 causal 어텐션 | 다음 토큰 예측 | GPT 계열, 대부분의 LLM | 생성 |
| 인코더-디코더 | 둘 다 + cross-attention | 입력→출력 변환 | 원조 Transformer, T5 | 번역, 요약 |

## LLM 시대의 핵심 용어
| 용어 | 뜻 |
|---|---|
| 사전학습 / 미세조정 | 대규모 텍스트로 일반 능력 학습 / 특정 과제에 추가 학습 |
| In-context learning, few-shot | 가중치 변경 없이 프롬프트의 예시만으로 과제 수행 (GPT-3) |
| Temperature, top-p | 생성의 무작위성 조절 |
| Hallucination | 그럴듯하지만 사실이 아닌 출력 |
| RAG | 외부 문서를 검색해 프롬프트에 넣고 생성 |
| LoRA / PEFT | 일부 저랭크 행렬만 학습하는 저비용 미세조정 |
| RLHF | 사람 선호 피드백으로 강화학습 (InstructGPT) |
| Agent, tool use | 모델이 도구를 호출하며 여러 단계로 문제 해결 (ReAct) |
| Benchmark / eval | 능력·안전성·편향을 재는 시험 (예: BBQ) |
| VLM | 이미지 인코더(ViT/CLIP)의 출력을 LLM 입력 공간에 연결한 멀티모달 모델 (LLaVA) |

## 추천 읽기 순서
1. [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/) (그림)
2. [3Blue1Brown — Transformers](https://www.youtube.com/watch?v=wjZofJX0v4M) (영상)
3. [Attention Is All You Need](https://arxiv.org/abs/1706.03762) (논문 — 3절 중심으로)
4. [Karpathy — Let's build GPT](https://www.youtube.com/watch?v=kCc8FmEb1nY) (직접 구현)
5. [The Annotated Transformer](https://nlp.seas.harvard.edu/annotated-transformer/) (논문+코드 대조)
