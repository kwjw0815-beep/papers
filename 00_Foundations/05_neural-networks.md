# 신경망 (Neural Networks)

## 왜 필요한가
딥러닝 논문은 대부분 "기존 구조에 부품 하나를 바꿨더니 좋아졌다"는 이야기다. 부품(층, 활성화, 정규화, 잔차 연결, 손실)의 이름과 역할을 알면 논문의 Method 절이 읽힌다.

## 최소한 이것만
| 개념 | 직관 | 정의 |
|---|---|---|
| 뉴런 / 층 (layer) | 입력의 가중합에 비선형 함수를 씌움 | $h=\sigma(Wx+b)$ |
| 활성화 함수 | 비선형성. 없으면 층을 쌓아도 선형 모델 | ReLU $\max(0,x)$, sigmoid, tanh, GELU |
| MLP (다층 퍼셉트론) | 완전연결 층을 여러 개 쌓은 것 | Feed-forward network |
| 순전파 (forward) | 입력 → 출력 계산 | |
| 손실 함수 | 예측과 정답의 차이 | 회귀: MSE / 분류: cross-entropy |
| softmax | 점수(logit)를 합이 1인 확률로 | $p_i=e^{z_i}/\sum_j e^{z_j}$ |
| 역전파 (backprop) | 출력에서부터 연쇄법칙으로 각 가중치의 기울기 계산 | → [미적분·최적화](02_calculus-optimization.md) |
| 파라미터 수 | 모델 크기. 학습되는 숫자의 개수 | "7B 모델" = 70억 개 |

**학습 루프 (모든 딥러닝 코드의 뼈대)**
```python
for x, y in dataloader:          # 미니배치
    pred = model(x)              # 순전파
    loss = loss_fn(pred, y)      # 손실
    optimizer.zero_grad()
    loss.backward()              # 역전파: 기울기 계산
    optimizer.step()             # 파라미터 업데이트
```

## 한 단계 더 — 논문에 계속 나오는 부품
| 부품 | 해결하는 문제 | 원 논문 |
|---|---|---|
| Dropout | 과적합 — 학습 중 뉴런을 무작위로 끔 | Srivastava et al., 2014 |
| Batch / Layer Normalization | 학습 불안정 — 층 입력의 분포를 정규화 | Ioffe & Szegedy, 2015 |
| 잔차 연결 (residual / skip connection) | 깊어지면 학습이 안 됨 — $y=x+F(x)$로 지름길 | ResNet, 2015 |
| Adam / AdamW | 학습률 조절 | Kingma & Ba, 2014 |
| Weight decay, early stopping, data augmentation | 과적합 | |
| 학습률 스케줄 (warmup, cosine) | 초반 불안정·후반 미세조정 | |

**구조별 귀납적 편향 (inductive bias)** — 데이터 형태에 맞춘 가정
- **CNN:** 이미지. 작은 필터를 전체에 공유 → 위치가 달라도 같은 패턴 인식.
- **RNN / LSTM:** 순서 데이터. 이전 상태를 다음으로 전달. 긴 의존성에서 기울기 소실.
- **Transformer:** 모든 위치가 서로를 직접 참조. → [어텐션·Transformer](06_attention-transformer.md)

**표현 학습·전이 학습**
- 신경망의 중간 층 출력 = 입력의 **표현(representation, embedding)**.
- 큰 데이터로 **사전학습(pre-training)** 후 내 과제에 **미세조정(fine-tuning)** 하는 것이 현대의 기본 방식.

## 자주 헷갈리는 점
- logit(softmax 전 점수) ≠ 확률.
- `model.train()` / `model.eval()` — Dropout·BatchNorm은 학습과 추론에서 다르게 동작한다.
- 손실이 `nan`이면: 학습률이 너무 크거나, log(0), 기울기 폭주.
- 큰 모델이 항상 과적합하는 것은 아니다 (→ Deep Double Descent).

## 더 공부할 자료
- 영상: [3Blue1Brown — But what is a neural network?](https://www.youtube.com/watch?v=aircAruvnKk) → [Karpathy — micrograd](https://www.youtube.com/watch?v=VMj-3S1tku0)
- 책: [Dive into Deep Learning](https://d2l.ai/) · [Understanding Deep Learning](https://udlbook.github.io/udlbook/) · [Deep Learning (Goodfellow)](https://www.deeplearningbook.org/)
- 강의: [fast.ai](https://course.fast.ai/) · [CS231n](https://cs231n.stanford.edu/) 강의노트
