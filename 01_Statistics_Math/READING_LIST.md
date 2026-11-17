# 필독 자료 — Statistics Math

통계적 사고방식과 추론의 기본기. 모든 분야의 바탕이 된다.

> **읽는 법:** ①→②→③ 순서. **★** 는 먼저 읽을 코어 자료, **🆕** 는 2025~2026년에 나온 자료다.  
> `선수 지식`의 문서를 먼저 훑고 오면 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.  
> 읽기 가이드·실습 과제·기억 점검 퀴즈는 [PRACTICE.md](PRACTICE.md), 실습 노트북은 [LABS.md](../LABS.md).

**먼저 읽을 것 (★)**: Statistical Modeling: The Two Cultures → The ASA Statement on p-Values

## ① 입문

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 영상 | **[Essence of Linear Algebra](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab)**<br>3Blue1Brown | 선형대수를 그림으로 이해하는 가장 빠른 길 | [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 영상 | **[StatQuest (채널)](https://www.youtube.com/@statquest)**<br>Josh Starmer | 통계·ML 개념을 10~20분 단위로 아주 쉽게 설명 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 영상 | **[But what is the Central Limit Theorem?](https://www.youtube.com/watch?v=zeJD6dqJ5lo)**<br>3Blue1Brown · YouTube | 표본 평균이 왜 정규분포로 모이는지 그림으로 이해 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 영상 | **[Bayes theorem, the geometry of changing beliefs](https://www.youtube.com/watch?v=HZGCoVF3YvM)**<br>3Blue1Brown · YouTube | 베이즈 정리를 면적 그림으로 이해 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 강의 | **[Statistics 110: Probability](https://projects.iq.harvard.edu/stat110)** †<br>Joe Blitzstein, Harvard | 확률론 입문의 정석 (강의 영상·교재 무료) | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 책 | 🆕 **[Think Stats (3rd ed.)](https://allendowney.github.io/ThinkStats/)**<br>Allen Downey | Python 코드로 배우는 통계 (노트북 무료, Colab 실행 가능) | [확률·통계](../00_Foundations/03_probability-statistics.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 웹 | **[Seeing Theory](https://seeing-theory.brown.edu/)**<br>Brown Univ. | 확률·통계 개념을 인터랙티브 시각화로 체험 | [확률·통계](../00_Foundations/03_probability-statistics.md) |

## ② 핵심

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 강의 | **[MIT 18.06 Linear Algebra](https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2010/)**<br>Gilbert Strang | 선형대수 표준 강의 | [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 강의 | **[Statistical Rethinking (2024 강의)](https://github.com/rmcelreath/stat_rethinking_2024)**<br>Richard McElreath · GitHub | 베이지안 사고와 인과 모형을 함께 가르치는 강의 (영상 무료) | [확률·통계](../00_Foundations/03_probability-statistics.md) · [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 책 | **[An Introduction to Statistical Learning (ISLR/ISLP)](https://www.statlearning.com/)**<br>James et al. | 통계학습 입문서 (PDF 무료, Python 판 있음) | [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 책 | **[Mathematics for Machine Learning](https://mml-book.github.io/)**<br>Deisenroth et al. | ML에 필요한 수학만 골라 정리 (PDF 무료) | [선형대수](../00_Foundations/01_linear-algebra.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 책 | **[Regression and Other Stories](https://avehtari.github.io/ROS-Examples/)**<br>Gelman, Hill, Vehtari | 회귀를 "해석"하는 법을 사례로 배우는 책 (PDF 무료) | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | ★ **[Statistical Modeling: The Two Cultures](https://doi.org/10.1214/ss/1009213726)**<br>Breiman, 2001 · DOI | "데이터 모델링 vs 알고리즘 모델링" — 통계와 ML의 관점 차이를 이해하는 필독 에세이 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Why Most Published Research Findings Are False](https://doi.org/10.1371/journal.pmed.0020124)**<br>Ioannidis, 2005 · DOI | 검정력·사전확률·편향이 낮으면 "유의한" 결과도 대부분 거짓 — 재현성 위기의 출발점 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[To Explain or to Predict?](https://doi.org/10.1214/10-STS330)**<br>Shmueli, 2010 · DOI | 설명 모델과 예측 모델은 목적·평가가 다르다는 점을 정리 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[The Statistical Crisis in Science (garden of forking paths)](https://doi.org/10.1511/2014.111.460)**<br>Gelman & Loken, 2014 · DOI | 분석 선택지가 많으면 의도하지 않아도 p-해킹이 된다 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | ★ **[The ASA Statement on p-Values: Context, Process, and Purpose](https://doi.org/10.1080/00031305.2016.1154108)**<br>Wasserstein & Lazar, 2016 · DOI | p-value를 올바르게 해석하는 6원칙. 짧고 실무에 바로 쓰임 | [확률·통계](../00_Foundations/03_probability-statistics.md) |

## ③ 심화

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 책 | **[The Elements of Statistical Learning](https://hastie.su.domains/ElemStatLearn/)**<br>Hastie, Tibshirani, Friedman | ISLR의 심화판 (PDF 무료) | [선형대수](../00_Foundations/01_linear-algebra.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 책 | **[Computer Age Statistical Inference](https://hastie.su.domains/CASI/)**<br>Efron & Hastie | 빈도주의·베이지안·ML을 역사 순으로 잇는 책 (PDF 무료) | [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Bootstrap Methods: Another Look at the Jackknife](https://doi.org/10.1214/aos/1176344552)**<br>Efron, 1979 · DOI | 부트스트랩의 원전. 신뢰구간을 시뮬레이션으로 구하는 발상 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Controlling the False Discovery Rate](https://doi.org/10.1111/j.2517-6161.1995.tb02031.x)**<br>Benjamini & Hochberg, 1995 · DOI | 다중검정 보정(FDR). 지표를 여러 개 보는 A/B 테스트에서 필수 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Regression Shrinkage and Selection via the Lasso](https://doi.org/10.1111/j.2517-6161.1996.tb02080.x)**<br>Tibshirani, 1996 · DOI | L1 정규화의 원전. 변수 선택과 과적합 제어 | [선형대수](../00_Foundations/01_linear-algebra.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[The Matrix Calculus You Need For Deep Learning](https://arxiv.org/abs/1802.01528)**<br>Parr & Howard, 2018 · arXiv 1802.01528 | 딥러닝 논문의 행렬 미분 표기를 읽기 위한 최소 지식 | [선형대수](../00_Foundations/01_linear-algebra.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) |
| ⬜ | 논문 | **[Moving to a World Beyond "p < 0.05"](https://doi.org/10.1080/00031305.2019.1583913)**<br>Wasserstein, Schirm, Lazar, 2019 · DOI | ASA 성명의 후속편. "유의하다"는 말 대신 무엇을 보고할 것인가 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Bayesian Workflow](https://arxiv.org/abs/2011.01808)**<br>Gelman et al., 2020 · arXiv 2011.01808 | 모형 설정→점검→비교의 반복 과정 전체를 정리 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Prediction-Powered Inference](https://arxiv.org/abs/2301.09633)**<br>Angelopoulos et al., 2023 · arXiv 2301.09633 | ML 예측값을 섞어 쓰면서도 유효한 신뢰구간을 얻는 방법 (LLM 평가에도 쓰임) | [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |

† 표시는 이 환경에서 접속이 차단되어 자동 확인을 못 한 링크(널리 알려진 주소).

---
링크 확인: 2026-11-10(기존 자료), 2026-11-16~17(추가 자료) — arXiv API · Crossref · HTTP 응답 · YouTube · GitHub로 제목 대조
