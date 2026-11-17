# Q&A 대화 정리 — ResNet (Deep Residual Learning)

> 자료를 읽은 뒤 나눈 질문과 답변을 정리하는 노트.
> 아직 실제 대화가 없어서, 아래 두 항목은 [워크북](../../00_Foundations/10_paper-reading-workbook.md)의 **작성 예시**로 넣어 둔 자문자답이다. 직접 질문을 하면 Q3부터 이어서 기록된다.

## Q1. (예시) 지름길을 더하기만 했는데 왜 학습이 쉬워지나? 직관적으로 설명하면?
- **날짜:** 2026-11-16
- **답변 요약:** 두 가지 관점이 있다. (1) **목표가 쉬워진다** — 블록이 "입력을 어떻게 바꿀지"만 배우면 되므로, 바꿀 필요가 없을 때는 0을 출력하면 된다. 논문이 제시한 동기다. (2) **기울기의 통로가 생긴다** — y = x + F(x) 를 미분하면 ∂y/∂x = 1 + ∂F/∂x 이므로, F 쪽 기울기가 작아져도 "1"을 통해 앞쪽 층까지 신호가 전달된다. 이 관점은 후속 논문(*Identity Mappings in Deep Residual Networks*)에서 수식으로 전개된다.
- **핵심 포인트:** 논문 본문이 직접 주장하는 것은 (1)이고, (2)는 널리 쓰이는 보충 설명이다. 논문은 원인을 단정하지 않는다는 점을 구분해서 기억할 것.
- **추가로 확인할 것:** Veit et al. (2016)의 "ResNet은 얕은 경로들의 앙상블처럼 동작한다"는 해석 → [references.md](references.md)

## Q2. (예시) Transformer의 `Add & Norm`이 이 논문과 같은 것인가?
- **날짜:** 2026-11-16
- **답변 요약:** `Add`가 잔차 연결이다. Transformer의 각 하위 층(어텐션, 피드포워드)은 `x + Sublayer(x)` 형태이고, *Attention Is All You Need* 가 이 논문을 인용한다. 정규화는 BatchNorm 대신 LayerNorm을 쓴다(시퀀스 길이가 제각각이라 배치 통계가 불안정하기 때문).
- **핵심 포인트:** 잔차 연결은 이미지 전용 기법이 아니라 "깊은 망을 학습시키는 일반 부품"이다.
- **추가로 확인할 것:** [어텐션·Transformer 기초](../../00_Foundations/06_attention-transformer.md)의 블록 구조 그림, [Lab 02](../labs/lab02_training_dynamics.ipynb) 직접 해보기 2번(BatchNorm vs LayerNorm)

---
## 배운 점 요약
- 과적합과 degradation은 **학습 곡선**으로 구별한다.
- 좋은 실험은 한 요소만 다르게 만든 비교군에서 나온다.
