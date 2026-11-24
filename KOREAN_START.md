# 🇰🇷 한국어로 시작하기

이 저장소의 필독 자료는 대부분 영어다. 영어가 막막해서 시작을 못 하고 있다면 이 문서부터 본다.
**개념은 한국어로 잡고, 영어 원문은 조금씩 늘려 가는 것**이 목표다. 처음부터 영어 논문을 끝까지 읽을 필요는 없다.

- 각 분야 폴더의 `READING_LIST.md` 맨 위에 **🇰🇷 한국어로 시작하기** 표가 있다(★ = 한국어로 먼저 볼 자료, 🆕 = 2025~2026 자료).
- 영어 표에서도 한국어판·한국어 해설이 있는 자료에는 🇰🇷 링크를 달았다.
- 모든 링크는 2026-11-23~24에 실제로 열어 제목을 확인했다. 책은 알라딘 상품 페이지로 연결한다.

## 목차
1. [세 가지 원칙](#1-세-가지-원칙)
2. [한국어 6주 시작 경로](#2-한국어-6주-시작-경로)
3. [분야별 ★ 한국어 자료](#3-분야별--한국어-자료)
4. [영어 논문을 한국어 도움을 받아 읽는 요령](#4-영어-논문을-한국어-도움을-받아-읽는-요령)
5. [최신 소식을 한국어로 따라가기](#5-최신-소식을-한국어로-따라가기)
6. [한국어 LLM과 한국 모델](#6-한국어-llm과-한국-모델)

---

## 1. 세 가지 원칙

1. **번역서가 있으면 번역서로 읽는다.** 이 저장소의 필독서 중 상당수는 한국어판이 있다(*핸즈온 머신러닝*, *밑바닥부터 만들면서 배우는 LLM*, *핸즈온 LLM*, *AI 엔지니어링*, *머신러닝 시스템 설계*, *A/B 테스트*, *실무로 통하는 인과추론*, *예측: 원리와 실제* 등). 내용이 같으므로 영어판을 고집할 이유가 없다.
2. **논문은 한국어 해설 → 영어 원문 순서로.** 한국어 리뷰 영상이나 강의로 구조를 먼저 잡고, 원문에서는 초록·그림·표·결론만 읽는다. 그것만으로도 [논문 읽기 워크북](00_Foundations/10_paper-reading-workbook.md)의 1·2차 읽기를 할 수 있다.
3. **용어는 영어로 기억한다.** 설명은 한국어로 들어도 `overfitting`, `attention`, `p-value` 같은 용어는 영어 원어를 함께 적는다. 영어 자료로 넘어갈 때 가장 큰 장벽이 용어다. → [용어집](00_Foundations/glossary.md)

## 2. 한국어 6주 시작 경로

[워크북의 6주 계획](00_Foundations/10_paper-reading-workbook.md#11-6주-훈련-계획)과 같은 흐름을 한국어 자료로 바꾼 것이다. 하루 1~2시간 기준. 매주 마지막에는 해당 실습 노트북을 돌리고, 영어 원문은 "그림과 표만" 확인한다.

| 주 | 한국어로 공부할 것 | 실습 | 영어 원문 (그림·표만) |
|---|---|---|---|
| 1 | 수학 직관: [3Blue1Brown 한국어 — 선형대수학의 본질](https://www.youtube.com/playlist?list=PLkoaXOTFHiqhVDo0nWybNmihCP_4BjOFR) · [공돌이의 수학정리노트](https://angeloyeo.github.io/) / 도구: [점프 투 파이썬](https://wikidocs.net/book/1) ‡ · [생활코딩 SQL](https://www.youtube.com/playlist?list=PLuHgQVnccGMCgrP_9HL3dAcvdt8qOZxjW) | [DL Lab 01](03_Deep_Learning/labs/lab01_backprop_from_scratch.ipynb) 1절 | - |
| 2 | 통계: [데이터 사이언스 스쿨](https://datascienceschool.net/intro.html)의 확률·통계 · [김성범 교수 P-Value 강의](https://www.youtube.com/watch?v=tpow70KGTYY) · 책 [데이터 과학을 위한 통계](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=269943212) | [통계 Lab 01](01_Statistics_Math/labs/lab01_sampling_bootstrap_pvalues.ipynb) | ASA p-value 성명의 6원칙 표 |
| 3 | 머신러닝: [혼자 공부하는 머신러닝+딥러닝 (개정판)](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=361140631) + [저자 강의](https://www.youtube.com/playlist?list=PLJN246lAkhQihHwcbrZp9uuwgxQen5HS-) · [김성범 교수 핵심 머신러닝](https://www.youtube.com/playlist?list=PLpIPLT0Pf7IoTxTCi2MEQ94MZnHaxrP0j) (부스팅·SHAP 편) | [ML Lab 01](02_Machine_Learning/labs/lab01_validation_leakage_metrics.ipynb), [Lab 02](02_Machine_Learning/labs/lab02_boosting_from_scratch_shap.ipynb) | XGBoost 논문 2절의 식 |
| 4 | 딥러닝: [밑바닥부터 시작하는 딥러닝 1](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=356399264) · [동빈나 ResNet 리뷰](https://www.youtube.com/watch?v=671BsKl8d0E) → [ResNet 풀이 예시 노트](03_Deep_Learning/2026-11-16_resnet-deep-residual-learning/summary.md) | [DL Lab 02](03_Deep_Learning/labs/lab02_training_dynamics.ipynb) | ResNet Figure 1, Table 2, Figure 4 |
| 5 | LLM: [3Blue1Brown 한국어 트랜스포머](https://www.youtube.com/watch?v=g38aoGttLhI)·[어텐션](https://www.youtube.com/watch?v=_Z3rXeJahMs) · [밑바닥부터 만들면서 배우는 LLM](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=372272431) + [역자 강의](https://www.youtube.com/playlist?list=PLJN246lAkhQhgakhcxz-5GwG_NYuJgSv1) | [LLM Lab 01](04_NLP_LLM/labs/lab01_tokenizer_attention_from_scratch.ipynb), [tiny GPT 학습](12_Open_Models/labs/lab02_train_tiny_gpt_end_to_end.ipynb) | Attention Is All You Need의 Figure 1과 식 (1) |
| 6 | 관심 분야 하나: **실험** [A/B 테스트 1장 한국어 PDF](https://experimentguide.com/wp-content/uploads/2022/07/2022-07-04-Trustworthy-Online-Controlled-Experiments_Korean_Chapter1.pdf) · [토스 A/B테스트 발표](https://www.youtube.com/watch?v=BljJ1jZ7e3U) / **추천** [추천 시스템 입문](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=315987513) · [하이퍼커넥트 추천 글](https://hyperconnect.github.io/2024/10/21/beyond-collaborative-filtering.html) / **시계열** [예측: 원리와 실제](https://otexts.com/fppkr/) | 해당 분야 Lab ([목록](LABS.md)) | 해당 분야 ★ 논문 하나 |

‡ 이 환경에서는 직접 접속이 막혀 검색 결과로 제목과 주소를 확인한 링크.

6주 뒤에는 영어 원문 비중을 늘린다. 다음 단계: 원문의 서론 마지막 문단(기여 목록)과 한계 절까지 영어로 읽기 → 그다음 방법 절.

## 3. 분야별 ★ 한국어 자료

각 폴더 `READING_LIST.md`의 🇰🇷 표에서 ★가 붙은 자료다. 전체 목록은 링크된 표에서 본다.

| 분야 | ★ 먼저 볼 한국어 자료 | 전체 |
|---|---|---|
| 통계·수학 | [공돌이의 수학정리노트](https://angeloyeo.github.io/) · [3Blue1Brown 한국어](https://www.youtube.com/playlist?list=PLkoaXOTFHiqhVDo0nWybNmihCP_4BjOFR) · [데이터 사이언스 스쿨](https://datascienceschool.net/intro.html) | [01](01_Statistics_Math/READING_LIST.md) |
| 머신러닝 | [혼자 공부하는 머신러닝+딥러닝](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=361140631) · [김성범 교수 핵심 머신러닝](https://www.youtube.com/playlist?list=PLpIPLT0Pf7IoTxTCi2MEQ94MZnHaxrP0j) | [02](02_Machine_Learning/READING_LIST.md) |
| 딥러닝 | [밑바닥부터 시작하는 딥러닝 1](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=356399264) · [Easy! 딥러닝](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=352995281) · [파이토치 한국어 튜토리얼](https://tutorials.pytorch.kr/) · [동빈나 논문 리뷰](https://www.youtube.com/playlist?list=PLRx0vPvlEmdADpce8aoBhNnDaaHQN1Typ) | [03](03_Deep_Learning/READING_LIST.md) |
| NLP·LLM | [딥 러닝을 이용한 자연어 처리 입문](https://wikidocs.net/book/2155) ‡ · [3Blue1Brown 한국어](https://www.youtube.com/watch?v=g38aoGttLhI) · [밑바닥부터 만들면서 배우는 LLM](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=372272431) | [04](04_NLP_LLM/READING_LIST.md) |
| 컴퓨터 비전 | [컴퓨터 비전과 딥러닝 (오일석)](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=308306489) · [밑바닥부터 시작하는 딥러닝 5](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=349271225) | [05](05_Computer_Vision/READING_LIST.md) |
| 추천 시스템 | [추천 시스템 입문](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=315987513) · [하이퍼커넥트 추천 시리즈](https://hyperconnect.github.io/2024/10/21/beyond-collaborative-filtering.html) | [06](06_Recommender_Systems/READING_LIST.md) |
| 시계열 | [예측: 원리와 실제 (FPP 한국어판, 무료)](https://otexts.com/fppkr/) · [김성범 교수 ARIMA 강의](https://www.youtube.com/watch?v=ma_L2YRWMHI) | [07](07_Time_Series/READING_LIST.md) |
| 인과추론·실험 | [Python으로 하는 인과추론 (무료)](https://causalinferencelab.github.io/Causal-Inference-with-Python/) · [실무로 통하는 인과추론](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=335177841) · [A/B 테스트](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=296254070) | [08](08_Causal_Inference_Experimentation/READING_LIST.md) |
| 데이터 엔지니어링·MLOps | [머신러닝 시스템 설계](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=312816103) · [MLOps for ALL](https://mlops-for-all.github.io/) · [생활코딩 SQL](https://www.youtube.com/playlist?list=PLuHgQVnccGMCgrP_9HL3dAcvdt8qOZxjW) | [09](09_Data_Engineering_MLOps/READING_LIST.md) |
| 분석·비즈니스 | [그로스 해킹](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=259675310) · [데이터 분석가가 반드시 알아야 할 모든 것](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=345480064) | [10](10_Analytics_Business/READING_LIST.md) |
| 커리어·동향 | [SPRi AI Brief](https://discuss.pytorch.kr/tag/spri) · [AI 기본법](https://www.law.go.kr/LSW/lsRvsDocInfoR.do?lsiSeq=282791) · [AI 엔지니어 기술 면접 스터디](https://github.com/boost-devs/ai-tech-interview) | [11](11_Career_Trends/READING_LIST.md) |
| 공개 모델 | [KORMo (한국어 완전 공개 모델)](https://arxiv.org/abs/2510.09426) · [KORMo 개발일지 세미나](https://www.youtube.com/watch?v=yvLlNHFcT-Y) · [밑바닥부터 만들면서 배우는 LLM](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=372272431) | [12](12_Open_Models/READING_LIST.md) |

## 4. 영어 논문을 한국어 도움을 받아 읽는 요령

1. **한국어 해설을 먼저 본다.** 필독 목록의 🇰🇷 링크, 또는 아래 채널에서 같은 논문을 찾는다.
   - [PR12 딥러닝 논문읽기 모임](https://www.youtube.com/playlist?list=PL0oFI08O71gKjGhaWctTPvvM7_cVzsAtK) — 수백 편의 고전 논문
   - [동빈나 꼼꼼한 딥러닝 논문 리뷰와 코드 실습](https://www.youtube.com/playlist?list=PLRx0vPvlEmdADpce8aoBhNnDaaHQN1Typ) — 논문 + 코드
   - [DSBA 연구실](https://www.youtube.com/watch?v=0kgDve_vC1o) · [김성범 교수 (DMQA)](https://www.youtube.com/playlist?list=PLpIPLT0Pf7IoTxTCi2MEQ94MZnHaxrP0j) — 대학 강의 수준의 해설
   - [딥러닝논문읽기모임](https://www.youtube.com/watch?v=B7_ht9TDtIE) — 최신 논문
2. **원문은 HTML로 연다.** arXiv 주소의 `arxiv.org/abs/번호`를 `ar5iv.labs.arxiv.org/html/번호`로 바꾸면 웹페이지로 열린다. 웹페이지는 브라우저의 페이지 번역 기능을 쓸 수 있고, 수식과 그림이 그대로 남는다.
3. **번역은 문단 단위로, 용어는 원어로.** 번역기를 쓰더라도 노트에는 핵심 용어를 영어로 적는다. 번역이 이상한 문장은 대개 그 문장의 핵심 용어를 모른다는 신호다 → [용어집](00_Foundations/glossary.md)에 추가.
4. **노트는 한국어로 쓴다.** 이 저장소의 `summary.md`는 한국어로 쓰고 용어만 영어를 병기한다. 이해했는지는 한국어로 설명할 수 있는지로 판단한다.
5. **Claude에게 물어본다.** "이 문단을 한국어로 풀어서 설명해줘", "이 논문의 한국어 해설 자료 찾아줘" — 답은 그 논문 노트의 `qna.md`에 기록된다.

## 5. 최신 소식을 한국어로 따라가기

| 종류 | 자료 | 한 줄 |
|---|---|---|
| 월간 보고서 | [SPRi AI Brief](https://discuss.pytorch.kr/tag/spri) (소프트웨어정책연구소) | 매달 AI 정책·산업·기술·인력 동향. PyTorch KR에 호마다 소개된다 |
| 커뮤니티 | [PyTorch KR](https://discuss.pytorch.kr/) · [GeekNews](https://news.hada.io/) | 논문·뉴스 한국어 요약 |
| 기업 기술 블로그 | [하이퍼커넥트](https://hyperconnect.github.io/) · [컬리](https://helloworld.kurly.com/) · [카카오 (Kanana-2 개발기)](https://tech.kakao.com/posts/807) · [토스](https://toss.tech/) · [쏘카](https://tech.socarcorp.kr/) | 추천·실험·LLM·데이터 파이프라인의 실제 사례. 2025~2026년 글은 각 폴더 🇰🇷 표에 골라 두었다 |
| 컨퍼런스 영상 | [토스 SLASH](https://www.youtube.com/playlist?list=PL1DJtS1Hv1PiGXmgruP1_gM2TSvQiOsFL) · [우아콘 2025](https://www.youtube.com/playlist?list=PLgXGHBqgT2TuPhUGHTe1oFkWJDu3u6-Si) · [if(kakao)25](https://www.youtube.com/playlist?list=PLwe9WEhzDhwG1H81qHrjc05sj75cGa1fi) · 데이터야놀자 | 20~40분짜리 실무 발표 |
| 정책 | [AI 기본법 (2026-01-22 시행)](https://www.law.go.kr/LSW/lsRvsDocInfoR.do?lsiSeq=282791) · [독자 AI 파운데이션 모델 현황](https://www.korea.kr/news/policyNewsView.do?newsId=148970236) | 데이터·AI 직무에 직접 영향을 주는 제도 |

## 6. 한국어 LLM과 한국 모델

한국어를 다루는 모델과 평가는 영어 자료만으로는 알기 어렵다. 자세한 목록은 [04_NLP_LLM](04_NLP_LLM/READING_LIST.md)과 [12_Open_Models](12_Open_Models/READING_LIST.md)의 🇰🇷 표에 있다.

- **완전 공개 한국어 모델:** [KORMo](https://arxiv.org/abs/2510.09426) (KAIST, 2025) — 데이터·코드·중간 모델까지 공개. 공부 방법은 [12_Open_Models/PRACTICE.md](12_Open_Models/PRACTICE.md)의 KORMo 가이드.
- **가중치 공개 한국 모델의 보고서:** [K-EXAONE](https://arxiv.org/abs/2601.01739) · [Solar Open](https://arxiv.org/abs/2601.07022) · [A.X K1](https://arxiv.org/abs/2601.09200) (모두 2026, 정부 독자 AI 파운데이션 모델 프로젝트) · [Kanana-2 개발기 (한국어 블로그)](https://tech.kakao.com/posts/807)
- **한국어 평가:** [KMMLU](https://arxiv.org/abs/2402.11548) · [HAE-RAE Bench](https://arxiv.org/abs/2309.02706) · [CLIcK](https://arxiv.org/abs/2403.06412) · [KMMLU-Redux·Pro](https://arxiv.org/abs/2507.08924) · [KoBBQ](https://arxiv.org/abs/2307.16778) (편향, [BBQ 노트](04_NLP_LLM/2026-11-03_bbq-bias-benchmark-qa/summary.md)와 함께)
