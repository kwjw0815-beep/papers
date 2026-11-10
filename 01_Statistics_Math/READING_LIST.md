# 필독 자료 — Statistics Math

통계적 사고방식과 추론의 기본기. 모든 분야의 바탕이 된다.

> **읽는 법:** ①→②→③ 순서. `선수 지식` 열의 링크를 먼저 훑고 오면 훨씬 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.

## ① 입문

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 영상 | Essence of Linear Algebra | 3Blue1Brown | [링크](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) | 선형대수를 그림으로 이해하는 가장 빠른 길 | [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 영상 | StatQuest (채널) | Josh Starmer | [링크](https://www.youtube.com/@statquest) | 통계·ML 개념을 10~20분 단위로 아주 쉽게 설명 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 웹 | Seeing Theory | Brown Univ. | [링크](https://seeing-theory.brown.edu/) † | 확률·통계 개념을 인터랙티브 시각화로 체험 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 강의 | Statistics 110: Probability | Joe Blitzstein, Harvard | [링크](https://projects.iq.harvard.edu/stat110) † | 확률론 입문의 정석 (강의 영상·교재 무료) | [확률·통계](../00_Foundations/03_probability-statistics.md) |

## ② 핵심

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 강의 | MIT 18.06 Linear Algebra | Gilbert Strang | [링크](https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2010/) | 선형대수 표준 강의 | [선형대수](../00_Foundations/01_linear-algebra.md) |
| ⬜ | 책 | An Introduction to Statistical Learning (ISLR/ISLP) | James et al. | [링크](https://www.statlearning.com/) | 통계학습 입문서 (PDF 무료, Python 판 있음) | [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 책 | Mathematics for Machine Learning | Deisenroth et al. | [링크](https://mml-book.github.io/) | ML에 필요한 수학만 골라 정리 (PDF 무료) | [선형대수](../00_Foundations/01_linear-algebra.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | Statistical Modeling: The Two Cultures | Breiman, 2001 | [DOI](https://doi.org/10.1214/ss/1009213726) | "데이터 모델링 vs 알고리즘 모델링" — 통계와 ML의 관점 차이를 이해하는 필독 에세이 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | The ASA Statement on p-Values: Context, Process, and Purpose | Wasserstein & Lazar, 2016 | [DOI](https://doi.org/10.1080/00031305.2016.1154108) | p-value를 올바르게 해석하는 6원칙. 짧고 실무에 바로 쓰임 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | To Explain or to Predict? | Shmueli, 2010 | [DOI](https://doi.org/10.1214/10-STS330) | 설명 모델과 예측 모델은 목적·평가가 다르다는 점을 정리 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |

## ③ 심화

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 논문 | Bootstrap Methods: Another Look at the Jackknife | Efron, 1979 | [DOI](https://doi.org/10.1214/aos/1176344552) | 부트스트랩의 원전. 신뢰구간을 시뮬레이션으로 구하는 발상 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | Controlling the False Discovery Rate | Benjamini & Hochberg, 1995 | [DOI](https://doi.org/10.1111/j.2517-6161.1995.tb02031.x) | 다중검정 보정(FDR). 지표를 여러 개 보는 A/B 테스트에서 필수 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | Regression Shrinkage and Selection via the Lasso | Tibshirani, 1996 | [DOI](https://doi.org/10.1111/j.2517-6161.1996.tb02080.x) | L1 정규화의 원전. 변수 선택과 과적합 제어 | [선형대수](../00_Foundations/01_linear-algebra.md) · [미적분·최적화](../00_Foundations/02_calculus-optimization.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 책 | The Elements of Statistical Learning | Hastie, Tibshirani, Friedman | [링크](https://hastie.su.domains/ElemStatLearn/) | ISLR의 심화판 (PDF 무료) | [선형대수](../00_Foundations/01_linear-algebra.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |

† 표시는 이 환경에서 접속이 차단되어 자동 확인을 못 한 링크(널리 알려진 주소).

---
링크 확인일: 2026-11-10 (arXiv API · Crossref · HTTP 응답으로 제목 대조)
