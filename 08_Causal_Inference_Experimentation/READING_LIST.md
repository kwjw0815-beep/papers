# 필독 자료 — Causal Inference Experimentation

데이터사이언티스트 실무·면접에서 가장 차별화되는 영역. A/B 테스트 → 관찰 데이터 인과추론 순.

> **읽는 법:** 영어가 부담되면 바로 아래 **🇰🇷 한국어로 시작하기**부터 본다. 영어 자료는 ①→②→③ 순서. **★** 는 먼저 볼 코어 자료, **🆕** 는 2025~2026년에 나온 자료다.  
> `선수 지식`의 문서를 먼저 훑고 오면 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.  
> 읽기 가이드·실습 과제·기억 점검 퀴즈는 [PRACTICE.md](PRACTICE.md), 실습 노트북은 [LABS.md](../LABS.md).

## 🇰🇷 한국어로 시작하기

영어 자료가 막막하면 여기서 시작한다. **★** 표시가 한국어로 먼저 볼 자료다. 번역서는 아래 영어 표의 원서와 내용이 같고, 영어 표에서 한국어판이나 한국어 해설이 있는 자료에는 🇰🇷 링크를 달아 두었다.

| 유형 | 자료 | 왜 보나 |
|---|---|---|
| 웹책 | ★ **[Python으로 하는 인과추론 — 개념부터 실습까지](https://causalinferencelab.github.io/Causal-Inference-with-Python/)**<br>가짜연구소 인과추론팀 번역 (무료) · [GitHub](https://github.com/CausalInferenceLab/Causal-Inference-with-Python) | 아래 영어 목록 Causal Inference for the Brave and True의 한국어판 |
| 책·강의 | ★ **[실무로 통하는 인과추론 with 파이썬](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=335177841)**<br>마테우스 파쿠레 · 신진수·가짜연구소 인과추론팀 옮김 · 한빛미디어 · 2024 · [해설 영상](https://www.youtube.com/playlist?list=PLKKkeayRo4PWuwIL0_C7n_QQQ_at6CpoE) | 아래 영어 목록 Causal Inference in Python의 한국어판. 해설 영상 재생목록이 있다 |
| 책 | ★ **[A/B 테스트 — 신뢰도 높은 온라인 통제 실험](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=296254070)**<br>론 코하비 외 · 이기홍·김기영 옮김 · 에이콘 · 2022 · [1장 한국어 PDF (무료)](https://experimentguide.com/wp-content/uploads/2022/07/2022-07-04-Trustworthy-Online-Controlled-Experiments_Korean_Chapter1.pdf) | 아래 영어 목록 Trustworthy Online Controlled Experiments의 한국어판 |
| 영상 | 🆕 **[토스 데이터 분석가가 하는 진짜 A/B테스트](https://www.youtube.com/watch?v=BljJ1jZ7e3U)**<br>토스 · TMC25 | 국내 핀테크의 실제 실험 운영 |
| 영상 | 🆕 **[A/B테스트만으로는 부족합니다 — CRM 실험으로 이해하는 베이지안 최적화](https://www.youtube.com/watch?v=8-nDivx4lS4)**<br>데이터야놀자 2026 | A/B 테스트 다음 단계 |
| 영상 | 🆕 **[왜 프로덕트 팀은 A/B테스트를 사랑할까? (feat 인과추론)](https://www.youtube.com/watch?v=Y93V1_0_9a0)**<br>데이터야놀자 2025 | 실험과 인과추론의 관계를 실무 언어로 |
| 영상·슬라이드 | **[당신의 A/B Test를 신뢰할 수 없는 이유](https://www.youtube.com/watch?v=J4zjwJNYyPM)**<br>방태모 · 데이터야놀자 2023 · [슬라이드 PDF](https://be-favorite.github.io/Presentation_archive/materials/Datayanolja_2023_Trustworthy_ABtest.pdf) | Kohavi 책의 핵심 함정(SRM, peeking 등)을 한국어로 정리 |
| 영상 | 🆕 **[인과추론 특강 · 더블 머신러닝](https://www.youtube.com/playlist?list=PLKKkeayRo4PXdPDRYxM31o8yXyTR235ve)**<br>인과추론의 데이터과학 · [더블 머신러닝](https://www.youtube.com/watch?v=qiyOc_yjCOU) | 인과추론 기초 특강과 Double ML 강의 (2026) |
| 블로그 | **[Azar의 공정한 A/B test 운영 시스템 · A/B 테스트 자동 분석툴](https://hyperconnect.github.io/2020/08/26/azar-ab-test.html)**<br>하이퍼커넥트 · [자동 분석툴](https://hyperconnect.github.io/2021/02/26/auto-stats-test.html) | 국내 서비스의 실험 플랫폼 설계 |
| 책 | **[그로스 해킹](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=259675310)**<br>양승화 · 위키북스 · 2021 | 지표·실험·코호트 분석을 국내 서비스 맥락으로 |

## 🌐 영어 자료

**먼저 읽을 것 (★)**: Controlled experiments on the web → CUPED → Peeking at A/B Tests

## ① 입문

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 강의 | **[Introduction to Causal Inference](https://www.bradyneal.com/causal-inference-course)**<br>Brady Neal | ML 관점의 인과추론 강의 (영상·교재 무료) | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 책 | **[Causal Inference for the Brave and True](https://matheusfacure.github.io/python-causality-handbook/landing-page.html)**<br>Matheus Facure<br>🇰🇷 [한국어판](https://causalinferencelab.github.io/Causal-Inference-with-Python/) | Python 코드로 배우는 인과추론 (웹 무료) | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 책 | **[The Effect](https://theeffectbook.net/)**<br>Nick Huntington-Klein | 수식을 최소화한 직관 중심 입문서 (웹 무료) | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 블로그 | **[How Not To Run an A/B Test](https://www.evanmiller.org/how-not-to-run-an-ab-test.html)**<br>Evan Miller, 2010 | 중간에 들여다보고 멈추면 왜 틀리는지 가장 짧게 설명한 고전 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 블로그 | **[Decision Making at Netflix (실험 시리즈)](https://netflixtechblog.com/decision-making-at-netflix-33065fa06481)** †<br>Netflix Tech Blog, 2021 | A/B 테스트의 개념·오류·문화까지 다룬 연재 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |

## ② 핵심

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 책 | **[Trustworthy Online Controlled Experiments](https://experimentguide.com/)**<br>Kohavi, Tang, Xu<br>🇰🇷 [한국어판](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=296254070) · [1장 한국어 PDF](https://experimentguide.com/wp-content/uploads/2022/07/2022-07-04-Trustworthy-Online-Controlled-Experiments_Korean_Chapter1.pdf) | A/B 테스트의 교과서 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 책 | **[Causal Inference in Python](https://github.com/matheusfacure/causal-inference-in-python-code)**<br>Matheus Facure, 2023 · GitHub<br>🇰🇷 [한국어판](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=335177841) | 현업 관점(가격·마케팅·실험) 인과추론 — 코드 저장소 공개 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 책 | **[Causal Inference: What If](https://miguelhernan.org/whatifbook)**<br>Hernán & Robins | 인과추론의 정석 교과서 (PDF 무료) | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Estimating causal effects of treatments in randomized and nonrandomized studies](https://doi.org/10.1037/h0037350)**<br>Rubin, 1974 · DOI | 잠재적 결과(potential outcomes) 프레임워크의 원전 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | ★ **[Controlled experiments on the web: survey and practical guide](https://doi.org/10.1007/s10618-008-0114-1)**<br>Kohavi et al., 2009 · DOI<br>🇰🇷 [방태모 발표 (데이터야놀자)](https://www.youtube.com/watch?v=J4zjwJNYyPM) | 온라인 실험 실무 가이드의 고전 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Overlapping Experiment Infrastructure: More, Better, Faster Experimentation](https://doi.org/10.1145/1835804.1835810)**<br>Tang et al. (Google), 2010 · DOI | 수많은 실험을 동시에 돌리는 계층(layer) 구조 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | **[Online Controlled Experiments at Large Scale](https://doi.org/10.1145/2487575.2488217)**<br>Kohavi et al., 2013 · DOI | 대규모 실험 플랫폼 운영의 함정들 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | ★ **[Improving the Sensitivity of Online Controlled Experiments by Utilizing Pre-Experiment Data (CUPED)](https://doi.org/10.1145/2433396.2433413)**<br>Deng et al., 2013 · DOI | 실험 전 데이터로 분산 줄이기 — 현업 표준 기법 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | ★ **[Peeking at A/B Tests: Why it matters, and what to do about it](https://doi.org/10.1145/3097983.3097992)**<br>Johari et al., 2017 · DOI | 중간에 결과를 들여다보면 왜 틀리는가 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Diagnosing Sample Ratio Mismatch in Online Controlled Experiments](https://doi.org/10.1145/3292500.3330722)**<br>Fabijan et al., 2019 · DOI | SRM의 원인 분류와 진단 절차 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | **[Statistical Challenges in Online Controlled Experiments: A Review of A/B Testing Methodology](https://arxiv.org/abs/2212.11366)**<br>Larsen et al., 2022 · arXiv 2212.11366 | 분산 축소·순차 검정·간섭·장기 효과 등 현대 A/B 테스트 쟁점 총정리 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[A/B Testing Intuition Busters](https://doi.org/10.1145/3534678.3539160)**<br>Kohavi, Deng, Vermeer, 2022 · DOI | p-value 오해, 사후 검정력, 낮은 검정력의 승자의 저주 등 흔한 오해 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |

## ③ 심화

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 책 | **[Applied Causal Inference Powered by ML and AI](https://arxiv.org/abs/2403.02467)**<br>Chernozhukov et al., 2024 · arXiv 2403.02467 | Double ML 저자들의 교과서 (PDF·노트북 무료) | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 블로그 | **[Choosing a Sequential Testing Framework — Comparisons and Discussions](https://engineering.atspotify.com/2023/03/choosing-sequential-testing-framework-comparisons-and-discussions)**<br>Spotify Engineering, 2023 | 순차 검정 방법들(GST, mSPRT 등)을 실무 관점에서 비교 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | **[The central role of the propensity score in observational studies for causal effects](https://doi.org/10.1093/biomet/70.1.41)**<br>Rosenbaum & Rubin, 1983 · DOI | 성향점수의 원전 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Synthetic Control Methods for Comparative Case Studies](https://doi.org/10.1198/jasa.2009.ap08746)**<br>Abadie et al., 2010 · DOI | 실험이 불가능할 때 가상의 대조군 만들기 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | **[Inferring causal impact using Bayesian structural time-series models (CausalImpact)](https://arxiv.org/abs/1506.00356)**<br>Brodersen et al., 2015 · arXiv 1506.00356 | 시계열 기반 개입 효과 추정 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Estimation and Inference of Heterogeneous Treatment Effects using Random Forests](https://arxiv.org/abs/1510.04342)**<br>Wager & Athey, 2015 · arXiv 1510.04342 | Causal Forest | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Always Valid Inference: Bringing Sequential Analysis to A/B Testing](https://arxiv.org/abs/1512.04922)**<br>Johari et al., 2015 · arXiv 1512.04922 | 언제 봐도 유효한 p-value·신뢰구간 (mSPRT) | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Double/Debiased Machine Learning for Treatment and Causal Parameters](https://arxiv.org/abs/1608.00060)**<br>Chernozhukov et al., 2016 · arXiv 1608.00060<br>🇰🇷 [인과추론의 데이터과학 강의](https://www.youtube.com/watch?v=qiyOc_yjCOU) | ML을 인과 효과 추정에 안전하게 쓰는 방법 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Generalized Random Forests](https://arxiv.org/abs/1610.01271)**<br>Athey, Tibshirani, Wager, 2016 · arXiv 1610.01271 | Causal Forest의 일반화 (grf, EconML의 기반) | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Meta-learners for Estimating Heterogeneous Treatment Effects using Machine Learning](https://arxiv.org/abs/1706.03461)**<br>Künzel et al., 2017 · arXiv 1706.03461 | S/T/X-learner — 업리프트 모델링의 기초 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Difference-in-Differences with Multiple Time Periods](https://arxiv.org/abs/1803.09015)**<br>Callaway & Sant'Anna, 2018 · arXiv 1803.09015 | 처치 시점이 다른 경우의 현대적 DiD | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | **[Synthetic Difference in Differences](https://arxiv.org/abs/1812.09970)**<br>Arkhangelsky et al., 2018 · arXiv 1812.09970 | DiD와 통제집단합성법의 결합 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | **[Top Challenges from the first Practical Online Controlled Experiments Summit](https://doi.org/10.1145/3331651.3331655)**<br>Gupta et al., 2019 · DOI | 13개 기업이 꼽은 실험의 난제 (장기 효과, 지표, 간섭) | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | **[Design and Analysis of Switchback Experiments](https://arxiv.org/abs/2009.00148)**<br>Bojinov, Simchi-Levi, Zhao, 2020 · arXiv 2009.00148 | 배달·차량호출처럼 간섭이 큰 서비스의 시간 단위 실험 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[DoWhy: An End-to-End Library for Causal Inference](https://arxiv.org/abs/2011.04216)**<br>Sharma & Kiciman, 2020 · arXiv 2011.04216 | 모형화→식별→추정→반박 4단계 절차를 강제하는 라이브러리 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[What's Trending in Difference-in-Differences? A Synthesis of the Recent Econometrics Literature](https://arxiv.org/abs/2201.01194)**<br>Roth et al., 2022 · arXiv 2201.01194 | 현대 DiD 논의를 한 편으로 정리 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |

† 표시는 이 환경에서 접속이 차단되어 자동 확인을 못 한 링크(널리 알려진 주소).

---
링크 확인: 2026-11-10(기존 자료), 2026-11-16~17(추가 자료), 2026-11-23~24(한국어 자료) — arXiv API · Crossref · HTTP 응답 · YouTube · GitHub로 제목 대조
