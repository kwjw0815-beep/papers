# 선형대수 (Linear Algebra)

## 왜 필요한가
ML에서 **데이터는 전부 벡터와 행렬**이다. 사용자 한 명 = 피처 벡터, 데이터셋 = 행렬, 단어 = 임베딩 벡터, 신경망의 한 층 = 행렬 곱. 논문의 수식 대부분은 "행렬을 곱하고 더한다"를 적어 놓은 것이다.

## 최소한 이것만
| 개념 | 직관 | 정의·표기 |
|---|---|---|
| 벡터 (vector) | 숫자 여러 개를 묶은 화살표/점 | $x \in \mathbb{R}^d$ : 실수 d개 |
| 행렬 (matrix) | 벡터를 다른 벡터로 바꾸는 변환(회전·늘리기) 또는 데이터 표 | $W \in \mathbb{R}^{m \times n}$ |
| 내적 (dot product) | 두 벡터가 **얼마나 같은 방향인지** | $x \cdot y = \sum_i x_i y_i$ |
| 노름 (norm) | 벡터의 길이 | L2: $\lVert x\rVert_2=\sqrt{\sum x_i^2}$, L1: $\sum \lvert x_i\rvert$ |
| 코사인 유사도 | 길이를 무시한 방향의 유사성 (−1~1) | $\frac{x\cdot y}{\lVert x\rVert\lVert y\rVert}$ |
| 행렬 곱 | 변환을 연달아 적용 | $(AB)_{ij}=\sum_k A_{ik}B_{kj}$, 차원: (m×n)(n×p)=(m×p) |
| 전치 (transpose) | 행과 열 바꾸기 | $A^\top$ |
| 랭크 (rank) | 행렬이 담고 있는 **독립적인 정보의 수** | 선형독립인 열(행)의 최대 개수 |

## 한 단계 더
- **고유값·고유벡터 (eigenvalue/eigenvector):** 변환을 해도 방향이 안 바뀌는 벡터와 그때 늘어나는 배율. $Av=\lambda v$.
- **SVD (특이값 분해):** 어떤 행렬이든 $A=U\Sigma V^\top$로 분해. 큰 특이값 몇 개만 남기면 **저랭크 근사** = 정보 압축.
- **PCA (주성분 분석):** 데이터가 가장 많이 퍼진 방향을 찾아 차원 축소. 공분산 행렬의 고유벡터 = 데이터 행렬의 SVD.
- **브로드캐스팅·텐서:** 3차원 이상 배열. 딥러닝 코드에서 `(batch, seq_len, dim)` 같은 shape을 읽는 능력이 실전에서는 가장 중요하다.

## 논문에서 만나는 모습
| 논문/주제 | 등장하는 선형대수 |
|---|---|
| Word2Vec, Sentence-BERT, CLIP | 임베딩 벡터의 내적·코사인 유사도로 "의미가 가깝다"를 측정 |
| Attention Is All You Need | $QK^\top$ = 질의와 키의 내적을 한꺼번에 계산한 행렬 |
| Matrix Factorization (추천) | 평점 행렬 ≈ 사용자 행렬 × 아이템 행렬ᵀ (저랭크 근사) |
| LoRA | 가중치 변화량을 $BA$ (랭크 r의 두 작은 행렬)로 제한 |
| Lasso / Ridge | L1 / L2 노름을 벌점으로 추가 |
| t-SNE, UMAP, PCA | 고차원 → 2차원 축소 |

## 자주 헷갈리는 점
- 행렬 곱은 순서를 바꾸면 안 된다 ($AB \ne BA$). 차원이 안 맞으면 대부분 여기서 버그가 난다.
- 내적이 크다 ≠ 유사하다. 벡터 길이가 길어도 내적은 커진다 → 그래서 코사인 유사도나 정규화를 쓴다.

## 더 공부할 자료
- 영상: [3Blue1Brown — Essence of Linear Algebra](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) (먼저 이것부터)
- 강의: [MIT 18.06 (Strang)](https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2010/)
- 책: [Mathematics for Machine Learning](https://mml-book.github.io/) 2~4장
