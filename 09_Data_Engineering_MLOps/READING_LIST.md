# 필독 자료 — Data Engineering MLOps

모델보다 시스템. 모델을 만들고 난 뒤에 생기는 문제를 다룬다.

> **읽는 법:** ①→②→③ 순서. **★** 는 먼저 읽을 코어 자료, **🆕** 는 2025~2026년에 나온 자료다.  
> `선수 지식`의 문서를 먼저 훑고 오면 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.  
> 읽기 가이드·실습 과제·기억 점검 퀴즈는 [PRACTICE.md](PRACTICE.md), 실습 노트북은 [LABS.md](../LABS.md).

**먼저 읽을 것 (★)**: Rules of Machine Learning → Hidden Technical Debt in Machine Learning Systems

## ① 입문

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 강의 | **[The Missing Semester of Your CS Education](https://missing.csail.mit.edu/)**<br>MIT | 셸·Git·디버깅 등 학교에서 안 가르치는 도구 | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 실습 | **[SQL Tutorial](https://mode.com/sql-tutorial/)**<br>Mode | 분석용 SQL을 기초부터 윈도 함수까지 | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 실습 | **[SQLBolt](https://sqlbolt.com/)**<br>SQLBolt | 브라우저에서 바로 푸는 SQL 기초 연습 | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 문서 | ★ **[Rules of Machine Learning: Best Practices for ML Engineering](https://developers.google.com/machine-learning/guides/rules-of-ml)**<br>Martin Zinkevich, Google | "첫 모델은 단순하게" 등 43개 실전 규칙 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 문서 | 🆕 **[uv 문서](https://docs.astral.sh/uv/)**<br>Astral | 요즘 표준이 된 Python 패키지·가상환경 도구 (nanochat 등 최신 저장소가 사용) | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 문서 | **[DuckDB 문서](https://duckdb.org/docs/)**<br>DuckDB | 노트북·로컬에서 대용량 분석 SQL — pandas와 함께 쓰기 | [도구](../00_Foundations/08_data-tools.md) |

## ② 핵심

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 강의 | **[Made With ML](https://madewithml.com/)**<br>Goku Mohandas | 설계→개발→배포→반복 MLOps 실습 (무료) | [도구](../00_Foundations/08_data-tools.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 강의 | **[Data Engineering Zoomcamp](https://github.com/DataTalksClub/data-engineering-zoomcamp)**<br>DataTalks.Club · GitHub | 수집→웨어하우스→변환→배치·스트리밍을 프로젝트로 (무료) | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 강의 | **[MLOps Zoomcamp](https://github.com/DataTalksClub/mlops-zoomcamp)**<br>DataTalks.Club · GitHub | 실험 추적·파이프라인·배포·모니터링 실습 (무료) | [도구](../00_Foundations/08_data-tools.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 책 | **[Designing Data-Intensive Applications](https://dataintensive.net/)**<br>Martin Kleppmann | 데이터 시스템 설계의 바이블 | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 책 | **[Designing Machine Learning Systems](https://github.com/chiphuyen/dmls-book)**<br>Chip Huyen, 2022 · GitHub | 데이터·피처·배포·모니터링·지속 학습까지 ML 시스템 설계 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | ★ **[Hidden Technical Debt in Machine Learning Systems](https://papers.nips.cc/paper/2015/hash/86df7dcfd896fcaf2674f757a2463eba-Abstract.html)**<br>Sculley et al., 2015 | ML 코드는 전체 시스템의 작은 일부 — MLOps의 출발점 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[The ML Test Score: A Rubric for ML Production Readiness and Technical Debt Reduction](https://doi.org/10.1109/BigData.2017.8258038)**<br>Breck et al., 2017 · DOI | 프로덕션 준비도 체크리스트 28항목 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[150 Successful Machine Learning Models: 6 Lessons Learned at Booking.com](https://doi.org/10.1145/3292500.3330744)**<br>Bernardi et al., 2019 · DOI | 오프라인 지표 향상이 비즈니스 성과로 이어지지 않는 이유 등 현업 교훈 | [ML 기초](../00_Foundations/04_ml-basics.md) · [인과·실험](../00_Foundations/07_causal-experiment-basics.md) |
| ⬜ | 논문 | **["Everyone wants to do the model work, not the data work": Data Cascades in High-Stakes AI](https://doi.org/10.1145/3411764.3445518)**<br>Sambasivan et al., 2021 · DOI | 데이터 품질 문제가 어떻게 연쇄적으로 커지는가 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Operationalizing Machine Learning: An Interview Study](https://arxiv.org/abs/2209.09125)**<br>Shankar et al., 2022 · arXiv 2209.09125 | ML 엔지니어 18명 인터뷰로 본 MLOps의 실제 (속도·검증·버전) | [ML 기초](../00_Foundations/04_ml-basics.md) |

## ③ 심화

| 상태 | 유형 | 자료 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|
| ⬜ | 강의 | **[Full Stack Deep Learning](https://fullstackdeeplearning.com/)**<br>FSDL | ML 제품을 끝까지 만드는 과정 | [도구](../00_Foundations/08_data-tools.md) · [신경망](../00_Foundations/05_neural-networks.md) |
| ⬜ | 블로그 | **[Building A Generative AI Platform](https://huyenchip.com/2024/07/25/genai-platform.html)**<br>Chip Huyen, 2024 | LLM 서비스의 구성요소(RAG·가드레일·라우터·캐시)를 단계별로 | [어텐션·Transformer](../00_Foundations/06_attention-transformer.md) · [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[MapReduce: Simplified Data Processing on Large Clusters](https://doi.org/10.1145/1327452.1327492)**<br>Dean & Ghemawat, 2004 · DOI | 분산 처리의 원형 | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[Resilient Distributed Datasets (Spark)](https://www.usenix.org/conference/nsdi12/technical-sessions/presentation/zaharia)**<br>Zaharia et al., 2012 | Spark의 핵심 추상화 | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[The Dataflow Model](https://doi.org/10.14778/2824032.2824076)**<br>Akidau et al. (Google), 2015 · DOI | 배치와 스트리밍을 하나의 모델로 (윈도·워터마크) | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[Failing Loudly: An Empirical Study of Methods for Detecting Dataset Shift](https://arxiv.org/abs/1810.11953)**<br>Rabanser et al., 2018 · arXiv 1810.11953 | 분포 변화 탐지 방법 비교 — 모니터링 설계의 근거 | [ML 기초](../00_Foundations/04_ml-basics.md) · [확률·통계](../00_Foundations/03_probability-statistics.md) |
| ⬜ | 논문 | **[Software Engineering for Machine Learning: A Case Study](https://doi.org/10.1109/ICSE-SEIP.2019.00042)**<br>Amershi et al. (Microsoft), 2019 · DOI | ML 개발 9단계 워크플로와 조직 성숙도 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[DuckDB: an Embeddable Analytical Database](https://doi.org/10.1145/3299869.3320212)**<br>Raasveldt & Mühleisen, 2019 · DOI | "분석용 SQLite"의 설계 | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[Challenges in Deploying Machine Learning: a Survey of Case Studies](https://arxiv.org/abs/2011.09926)**<br>Paleyes et al., 2020 · arXiv 2011.09926 | 배포 단계별 실패 사례 정리 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | **[Lakehouse: A New Generation of Open Platforms that Unify Data Warehousing and Advanced Analytics](https://www.cidrdb.org/cidr2021/papers/cidr2021_paper17.pdf)**<br>Armbrust et al., 2021 | 데이터 레이크 + 웨어하우스 통합 구조 | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | **[Machine Learning Operations (MLOps): Overview, Definition, and Architecture](https://arxiv.org/abs/2205.02302)**<br>Kreuzberger et al., 2022 · arXiv 2205.02302 | MLOps 용어·역할·구조 정리 | [ML 기초](../00_Foundations/04_ml-basics.md) |

---
링크 확인: 2026-11-10(기존 자료), 2026-11-16~17(추가 자료) — arXiv API · Crossref · HTTP 응답 · YouTube · GitHub로 제목 대조
