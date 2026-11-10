# 미적분·최적화 (Calculus & Optimization)

## 왜 필요한가
"모델을 학습한다" = **손실 함수(loss)를 최소로 만드는 파라미터를 찾는다**. 이를 위해 "파라미터를 조금 바꾸면 손실이 얼마나 변하는가(기울기)"를 계산하고 그 반대 방향으로 조금씩 이동한다. 이것이 거의 모든 ML 학습의 전부다.

## 최소한 이것만
| 개념 | 직관 | 정의 |
|---|---|---|
| 미분 (derivative) | 입력을 아주 조금 바꿀 때 출력의 변화율 | $f'(x)=\lim_{h\to0}\frac{f(x+h)-f(x)}{h}$ |
| 편미분 | 변수 하나만 움직였을 때의 변화율 | $\partial f/\partial x_i$ |
| 그래디언트 (gradient) | 편미분을 모은 벡터. **가장 가파르게 올라가는 방향** | $\nabla f=(\partial f/\partial x_1,\dots)$ |
| 연쇄법칙 (chain rule) | 함수를 겹쳐 쓰면 변화율은 곱해진다 | $\frac{dz}{dx}=\frac{dz}{dy}\cdot\frac{dy}{dx}$ |
| 손실 함수 (loss) | 예측이 얼마나 틀렸는지 한 숫자로 | MSE, cross-entropy 등 |
| 경사하강법 (gradient descent) | 기울기 반대 방향으로 한 걸음 | $\theta \leftarrow \theta-\eta\nabla L(\theta)$ |
| 학습률 (learning rate, $\eta$) | 보폭. 크면 발산, 작으면 느림 | 가장 중요한 하이퍼파라미터 |

## 한 단계 더
- **SGD (확률적 경사하강법):** 전체 데이터 대신 미니배치로 기울기를 **추정**. 빠르고, 잡음이 오히려 일반화에 도움이 되기도 한다.
- **모멘텀 / Adam:** 과거 기울기의 이동평균을 써서 진동을 줄이고(모멘텀), 파라미터마다 보폭을 자동 조절(Adam).
- **볼록 함수 (convex):** 그릇 모양 → 지역 최솟값 = 전역 최솟값. 선형·로지스틱 회귀는 볼록, 신경망은 비볼록.
- **정규화 (regularization):** 손실에 벌점 $\lambda\lVert\theta\rVert$를 더해 파라미터가 커지는 것을 막음 → 과적합 완화.
- **역전파 (backpropagation):** 연쇄법칙을 출력에서 입력 방향으로 효율적으로 적용하는 알고리즘. → [신경망](05_neural-networks.md)
- **2차 근사:** 부스팅(XGBoost)은 손실을 테일러 전개해 1차(gradient)·2차(hessian) 정보로 트리를 만든다.

## 논문에서 만나는 모습
| 논문 | 등장하는 내용 |
|---|---|
| Rumelhart et al. (1986) | 연쇄법칙으로 모든 층의 기울기 계산 |
| Adam | 1차·2차 모멘트 추정, bias correction |
| Friedman GBM / XGBoost | "함수 공간에서의 경사하강" — 잔차(음의 기울기)에 새 트리를 맞춤 |
| ResNet, BatchNorm | 기울기 소실·폭주(vanishing/exploding gradient)를 줄이는 구조 |
| Lasso | L1 벌점은 미분 불가능한 점이 있어 계수가 정확히 0이 됨 |

## 자주 헷갈리는 점
- 기울기는 손실이 **증가**하는 방향이다. 그래서 빼 준다.
- 손실이 줄지 않으면 가장 먼저 학습률을 의심한다.
- epoch(전체 데이터 1회) / batch(한 번에 넣는 묶음) / step·iteration(업데이트 1회)을 구분한다.

## 더 공부할 자료
- 영상: [3Blue1Brown — Neural Networks 시리즈](https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi) 2~4편 (경사하강·역전파)
- 영상: [Karpathy — micrograd](https://www.youtube.com/watch?v=VMj-3S1tku0)
- 책: [Mathematics for Machine Learning](https://mml-book.github.io/) 5, 7장
