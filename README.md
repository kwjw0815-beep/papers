Summary of ML papers I've read in recorded in Issues
Questions to ask myself when reading papers.. (Reference : Guide to Reading Academic Research Paper

1. What previous research and ideas were cited that this paper is building off of? (this info tends to live in the introduction)
2. Was there reasoning for performing this research, if so what was it? (introduction section)
3. Clearly list out the objectives of the study
4. Was any equipment/software used? (methods section)
5. What variables were measured during experimentation? (methods)
6. Were any statistical tests used? What were their results? (methods/results section)
7. What are the main findings? (results section)
8. How do these results fit into the context of other research and their 'field'? (discussion section)
9. Explain each figure and discuss their significance.
10. Can the results be reproduced and is there any code available?
11. Name the authors, year, and title of the paper!
12. Are any of the authors familiar, do you know their previous work? 
13. What key terms and concepts do I not know and need to look up in a dictionary, textbook, or ask someone?
14. What are your thoughts on the results? Do they seem valid?


---
## 폴더 구조
데이터사이언스 분야별 상위 폴더 아래에 자료 하나당 하위 폴더(`YYYY-MM-DD_주제-slug`)를 만들어 정리합니다.

```
<상위폴더>/<YYYY-MM-DD_주제-slug>/
├── summary.md      # 자료 요약 (논문은 위 14개 질문 기준)
├── qna.md          # 이후 나눈 질문·답변 정리
└── references.md   # 관련 논문·블로그·영상 추천
```

| 상위 폴더 | 범위 |
|---|---|
| [01_Statistics_Math](01_Statistics_Math) | 통계·확률·선형대수·최적화 |
| [02_Machine_Learning](02_Machine_Learning) | 고전 ML, 피처 엔지니어링, 모델 평가 |
| [03_Deep_Learning](03_Deep_Learning) | 딥러닝 일반 |
| [04_NLP_LLM](04_NLP_LLM) | NLP, LLM, RAG, 에이전트 |
| [05_Computer_Vision](05_Computer_Vision) | CV, 생성 모델 |
| [06_Recommender_Systems](06_Recommender_Systems) | 추천 시스템 |
| [07_Time_Series](07_Time_Series) | 시계열, 이상 탐지 |
| [08_Causal_Inference_Experimentation](08_Causal_Inference_Experimentation) | 인과추론, A/B 테스트 |
| [09_Data_Engineering_MLOps](09_Data_Engineering_MLOps) | 데이터 파이프라인, MLOps |
| [10_Analytics_Business](10_Analytics_Business) | 지표, 프로덕트 분석, 시각화 |
| [11_Career_Trends](11_Career_Trends) | 커리어, 업계 동향 |

템플릿은 [`_templates/`](_templates)에 있습니다.
