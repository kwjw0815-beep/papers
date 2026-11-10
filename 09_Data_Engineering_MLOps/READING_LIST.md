# 필독 자료 — Data Engineering MLOps

모델보다 시스템. 모델을 만들고 난 뒤에 생기는 문제를 다룬다.

> **읽는 법:** ①→②→③ 순서. `선수 지식` 열의 링크를 먼저 훑고 오면 훨씬 수월하다. 읽고 정리한 자료는 `상태`를 ✅로 바꾸고 노트 폴더를 연결한다.

## ① 입문

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 실습 | SQL Tutorial | Mode | [링크](https://mode.com/sql-tutorial/) | 분석용 SQL을 기초부터 윈도 함수까지 | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 강의 | The Missing Semester of Your CS Education | MIT | [링크](https://missing.csail.mit.edu/) | 셸·Git·디버깅 등 학교에서 안 가르치는 도구 | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 문서 | Rules of Machine Learning: Best Practices for ML Engineering | Martin Zinkevich, Google | [링크](https://developers.google.com/machine-learning/guides/rules-of-ml) | "첫 모델은 단순하게" 등 43개 실전 규칙 | [ML 기초](../00_Foundations/04_ml-basics.md) |

## ② 핵심

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 논문 | Hidden Technical Debt in Machine Learning Systems | Sculley et al., 2015 | [링크](https://papers.nips.cc/paper/2015/hash/86df7dcfd896fcaf2674f757a2463eba-Abstract.html) | ML 코드는 전체 시스템의 작은 일부 — MLOps의 출발점 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | The ML Test Score: A Rubric for ML Production Readiness and Technical Debt Reduction | Breck et al., 2017 | [DOI](https://doi.org/10.1109/BigData.2017.8258038) | 프로덕션 준비도 체크리스트 28항목 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | "Everyone wants to do the model work, not the data work": Data Cascades in High-Stakes AI | Sambasivan et al., 2021 | [DOI](https://doi.org/10.1145/3411764.3445518) | 데이터 품질 문제가 어떻게 연쇄적으로 커지는가 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 강의 | Made With ML | Goku Mohandas | [링크](https://madewithml.com/) | 설계→개발→배포→반복 MLOps 실습 (무료) | [도구](../00_Foundations/08_data-tools.md) · [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 책 | Designing Data-Intensive Applications | Martin Kleppmann | [링크](https://dataintensive.net/) | 데이터 시스템 설계의 바이블 | [도구](../00_Foundations/08_data-tools.md) |

## ③ 심화

| 상태 | 유형 | 제목 | 저자/출처 | 링크 | 왜 읽나 | 선수 지식 |
|---|---|---|---|---|---|---|
| ⬜ | 논문 | MapReduce: Simplified Data Processing on Large Clusters | Dean & Ghemawat, 2004 | [DOI](https://doi.org/10.1145/1327452.1327492) | 분산 처리의 원형 | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | Resilient Distributed Datasets (Spark) | Zaharia et al., 2012 | [링크](https://www.usenix.org/conference/nsdi12/technical-sessions/presentation/zaharia) | Spark의 핵심 추상화 | [도구](../00_Foundations/08_data-tools.md) |
| ⬜ | 논문 | Challenges in Deploying Machine Learning: a Survey of Case Studies | Paleyes et al., 2020 | [arXiv 2011.09926](https://arxiv.org/abs/2011.09926) | 배포 단계별 실패 사례 정리 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 논문 | Machine Learning Operations (MLOps): Overview, Definition, and Architecture | Kreuzberger et al., 2022 | [arXiv 2205.02302](https://arxiv.org/abs/2205.02302) | MLOps 용어·역할·구조 정리 | [ML 기초](../00_Foundations/04_ml-basics.md) |
| ⬜ | 강의 | Full Stack Deep Learning | FSDL | [링크](https://fullstackdeeplearning.com/) | ML 제품을 끝까지 만드는 과정 | [도구](../00_Foundations/08_data-tools.md) · [신경망](../00_Foundations/05_neural-networks.md) |

---
링크 확인일: 2026-11-10 (arXiv API · Crossref · HTTP 응답으로 제목 대조)
