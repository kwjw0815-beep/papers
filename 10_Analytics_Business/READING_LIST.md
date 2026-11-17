# 필독 자료 — Analytics Business

분석 결과를 올바르게 만들고(데이터 정리·지표), 잘 전달하는(시각화·글쓰기) 능력.

> **읽는 법:** ①→②→③ 순서. **★** 는 먼저 읽을 코어 자료, **🆕** 는 2025~2026년에 나온 자료다.  
> `선수 지식`의 문서를 먼저 훑고 오면 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.  
> 읽기 가이드·실습 과제·기억 점검 퀴즈는 [PRACTICE.md](PRACTICE.md), 실습 노트북은 [LABS.md](../LABS.md).

**먼저 읽을 것 (★)**: HEART → Tidy Data

## ① 입문

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 책 | **[Fundamentals of Data Visualization](https://clauswilke.com/dataviz/)**<br>Claus Wilke | 도구와 무관한 시각화 원칙 (웹 무료) | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 책 | **[Python Data Science Handbook](https://jakevdp.github.io/PythonDataScienceHandbook/)**<br>Jake VanderPlas | NumPy·pandas·Matplotlib·scikit-learn (웹 무료) | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 책 | **[Python for Data Analysis (3rd ed.)](https://wesmckinney.com/book/)**<br>Wes McKinney | pandas 창시자가 쓴 표준 교재 (웹 무료) | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 블로그 | **[Storytelling with Data](https://www.storytellingwithdata.com/)**<br>Cole Nussbaumer Knaflic | 데이터로 설득하는 법 | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 블로그 | **[데이터리안 블로그](https://datarian.io/blog)**<br>데이터리안 | 한국어 프로덕트 분석·SQL·지표 글 | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 웹 | **[From Data to Viz](https://www.data-to-viz.com/)**<br>Yan Holtz | 데이터 형태에 맞는 차트를 고르는 의사결정 나무 | [도구](../00_Foundations/08_data-tools.md) |

## ② 핵심

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 책 | **[Data Visualization: A Practical Introduction](https://socviz.co/)**<br>Kieran Healy | 왜 어떤 그래프는 잘 읽히는가 + ggplot 실습 (웹 무료) | [확률·통계](../00_Foundations/03_probability-statistics.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[Sex Bias in Graduate Admissions: Data from Berkeley](https://doi.org/10.1126/science.187.4175.398)**<br>Bickel et al., 1975 · DOI | 심슨의 역설의 대표 사례 — 집계 수준이 결론을 뒤집는다 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | **[Graphical Perception: Theory, Experimentation, and Application to the Development of Graphical Methods](https://doi.org/10.1080/01621459.1984.10478080)**<br>Cleveland & McGill, 1984 · DOI | 사람이 어떤 그래프를 정확히 읽는가 — 차트 선택의 근거 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | ★ **[Measuring the User Experience on a Large Scale: User-Centered Metrics for Web Applications (HEART)](https://doi.org/10.1145/1753326.1753687)**<br>Rodden et al., 2010 · DOI | Google의 지표 설계 프레임워크 (HEART, Goals-Signals-Metrics) | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | **[A Layered Grammar of Graphics](https://doi.org/10.1198/jcgs.2009.07098)**<br>Wickham, 2010 · DOI | 그래프를 데이터·기하·척도·좌표의 조합으로 보는 문법 (ggplot, plotnine, Altair의 기반) | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | ★ **[Tidy Data](https://doi.org/10.18637/jss.v059.i10)**<br>Wickham, 2014 · DOI | "변수=열, 관측=행" — 데이터 정리의 표준 원칙 | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[Seven Rules of Thumb for Web Site Experimenters](https://doi.org/10.1145/2623330.2623341)**<br>Kohavi et al., 2014 · DOI | 수많은 실험에서 얻은 지표·실험 경험칙 | [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | **[Ten Simple Rules for Better Figures](https://doi.org/10.1371/journal.pcbi.1003833)**<br>Rougier et al., 2014 · DOI | 그림 품질을 올리는 10가지 규칙 (짧음) | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[50 Years of Data Science](https://doi.org/10.1080/10618600.2017.1384734)**<br>Donoho, 2017 · DOI | 데이터 사이언스란 무엇인가를 역사적으로 정리 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Good enough practices in scientific computing](https://doi.org/10.1371/journal.pcbi.1005510)**<br>Wilson et al., 2017 · DOI | 데이터·코드·프로젝트 정리의 최소 기준 | [도구](../00_Foundations/08_data-tools.md) |

## ③ 심화

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 논문 | **[The Future of Data Analysis](https://doi.org/10.1214/aoms/1177704711)**<br>Tukey, 1962 · DOI | 탐색적 데이터 분석(EDA) 사고의 원류 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Datasheets for Datasets](https://arxiv.org/abs/1803.09010)**<br>Gebru et al., 2018 · arXiv 1803.09010 | 데이터셋 문서화 표준 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Model Cards for Model Reporting](https://arxiv.org/abs/1810.03993)**<br>Mitchell et al., 2018 · arXiv 1810.03993 | 모델 문서화 표준 — 성능을 집단별로 보고하기 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Statistical Paradises and Paradoxes in Big Data (I)](https://doi.org/10.1214/18-AOAS1161SF)**<br>Xiao-Li Meng, 2018 · DOI | 데이터가 커도 표본이 편향되면 무용 — 빅데이터 역설 | [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[DS-1000: A Natural and Reliable Benchmark for Data Science Code Generation](https://arxiv.org/abs/2211.11501)**<br>Lai et al., 2022 · arXiv 2211.11501 | LLM의 데이터 분석 코드 작성 능력 평가 | [도구](../00_Foundations/08_data-tools.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | **[Data Science at the Singularity](https://arxiv.org/abs/2310.00865)**<br>Donoho, 2023 · arXiv 2310.00865 | 데이터·코드·벤치마크 공유가 만든 "마찰 없는 재현성"이 AI 발전의 동력 | [확률·통계](../00_Foundations/03_probability-statistics.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Spider 2.0: Evaluating Language Models on Real-World Enterprise Text-to-SQL Workflows](https://arxiv.org/abs/2411.07763)**<br>Lei et al., 2024 · arXiv 2411.07763 | 실제 기업 DB 규모의 Text-to-SQL — AI에게 SQL을 맡길 때의 한계 파악 | [도구](../00_Foundations/08_data-tools.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |
| ⬜ | 논문 | 🆕 **[DABstep: Data Agent Benchmark for Multi-step Reasoning](https://arxiv.org/abs/2506.23719)**<br>Egg et al., 2025 · arXiv 2506.23719 | 실제 분석 업무형 다단계 과제에서 AI 에이전트가 어디까지 하는가 | [도구](../00_Foundations/08_data-tools.md) · [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) |

---
링크 확인: 2026-11-10(기존 자료), 2026-11-16~17(추가 자료) — arXiv API · Crossref · HTTP 응답 · YouTube · GitHub로 제목 대조
