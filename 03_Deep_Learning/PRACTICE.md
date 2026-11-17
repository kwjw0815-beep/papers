# 실습 가이드 — Deep Learning

[필독 목록](READING_LIST.md)의 자료를 **읽고 → 해 보고 → 기억하는** 순서로 쓰는 문서. 읽는 요령은 [논문 읽기 워크북](../00_Foundations/10_paper-reading-workbook.md), 노트북 실행법은 [LABS.md](../LABS.md).

## 이 폴더의 실습
- [lab01_backprop_from_scratch](labs/lab01_backprop_from_scratch.ipynb) — 역전파 직접 구현
- [lab02_training_dynamics](labs/lab02_training_dynamics.ipynb) — Adam·학습률·잔차 연결·드롭아웃
- 풀이 예시 노트: [ResNet](2026-11-16_resnet-deep-residual-learning/summary.md)

## 자료 유형별 기본 과제
| 유형 | 할 일 | 남기는 것 |
|---|---|---|
| 논문 | 1차 읽기(10분) → 주장-증거 표 → 14개 질문 노트 | `summary.md` + 기억 점검 질문 3개 |
| 영상·강의 | 보기 전에 "알고 싶은 것 3개"를 적고, 본 뒤 답을 쓴다. 코드가 나오면 따라 치지 말고 **멈춘 뒤 먼저 써 본다** | 미디어 노트(`summary_media.md`) |
| 책·문서 | 한 장을 읽고 책을 덮은 채 핵심 3줄을 쓴다. 연습문제·예제 코드를 하나 이상 실행 | 장별 3줄 요약 |
| 블로그·뉴스 | 주장 1개와 근거 1개를 뽑고, 근거의 출처(원 논문·데이터)를 따라가 본다 | 한 줄 메모 + 원출처 링크 |
| 도구·저장소 | 공식 예제 하나를 실행하고, 내 데이터(또는 실습 노트북의 데이터)에 적용 | 실행한 코드 조각 |

## ★ 코어 자료 가이드
### Deep Residual Learning for Image Recognition (ResNet)
[arXiv 1512.03385](https://arxiv.org/abs/1512.03385)

- **이 논문이 답하는 질문:** 층을 깊게 쌓으면 왜 학습 오차부터 나빠지고, 어떻게 해결하는가.
- **읽기 가이드:** [워크북](../00_Foundations/10_paper-reading-workbook.md)이 이 논문으로 훈련 1~5를 진행한다. Figure 1 → Figure 2 → Table 2 → Figure 4 순서.
- **실습:** Lab 02의 3절. 끝낸 뒤 [풀이 예시 노트](2026-11-16_resnet-deep-residual-learning/summary.md)와 내 노트를 비교.

**기억 점검**
1. degradation과 과적합의 차이는?
2. y = F(x) + x 에서 F가 배우는 것은?

<details><summary>답 확인</summary>

1. degradation은 층을 늘렸을 때 학습 오차 자체가 높아지는 것. 과적합은 학습 오차는 낮은데 테스트 오차가 높은 것.
2. 입력과 원하는 출력의 차이(잔차). 바꿀 것이 없으면 0만 배우면 된다.
</details>

### Adam: A Method for Stochastic Optimization
[arXiv 1412.6980](https://arxiv.org/abs/1412.6980)

- **이 논문이 답하는 질문:** 기울기의 크기가 파라미터마다·시점마다 다를 때 학습률을 어떻게 자동으로 맞출 것인가.
- **읽기 가이드:** Algorithm 1 상자를 종이에 옮겨 적고 기호 사전을 만든다(m, v, β1, β2, ε). 그다음 bias correction을 설명하는 절만 읽는다. 수렴 증명은 건너뛴다(이후 반례가 지적됨: *On the Convergence of Adam and Beyond*).
- **실습:** Lab 02의 1절(논문의 다섯 줄을 구현해 PyTorch와 대조)과 2절(학습률 민감도).

**기억 점검**
1. m과 v는 각각 무엇인가?
2. bias correction이 없으면?
3. Adam과 AdamW의 차이는?

<details><summary>답 확인</summary>

1. 기울기의 지수이동평균(1차 모멘트)과 기울기 제곱의 지수이동평균(2차 모멘트).
2. m, v가 0에서 시작해 초반에 0 쪽으로 치우쳐, 초기 스텝 크기가 왜곡된다.
3. AdamW는 weight decay를 기울기에 섞지 않고 파라미터에 직접 적용한다(decoupled).
</details>


## 그 밖의 자료
코어가 아닌 자료는 위의 "자료 유형별 기본 과제"를 따른다. 특정 자료의 읽기 가이드나 퀴즈가 필요하면 Claude에게 "○○ 실습 가이드 만들어줘"라고 요청하면 이 문서에 추가된다.
