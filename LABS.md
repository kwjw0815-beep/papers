# 실습 노트북 안내

논문의 핵심 주장을 **작은 실험으로 직접 확인**하는 노트북 모음. 모두 CPU에서 몇 분 안에 끝나도록 만들었고, 이 저장소를 만들 때 처음부터 끝까지 실행해 검증했다(실행 결과 포함).

## 실행 방법
- **Colab (설치 불필요):** 주소 `https://colab.research.google.com/github/kwjw0815-beep/papers/blob/main/<노트북 경로>` 로 연다. 예: [통계 Lab 01 열기](https://colab.research.google.com/github/kwjw0815-beep/papers/blob/main/01_Statistics_Math/labs/lab01_sampling_bootstrap_pvalues.ipynb) (main 브랜치에 병합된 뒤 동작)
- **내 컴퓨터:** 저장소를 받은 뒤 아래 실행
```bash
pip install -r requirements-labs.txt
```
```bash
jupyter lab
```

## 노트북 형식
1. 표: 다루는 논문과 확인할 것
2. `✍️ 예측` — 셀을 실행하기 **전에** 결과를 먼저 적는다
3. 실행과 해설
4. `직접 해보기` — 빈 셀에 스스로 풀기 → `정답 예시`
5. `논문으로 돌아가기` — 방금 한 것이 논문의 어느 그림·식인지
6. `기억 점검` — 답을 가리고 말로 설명

## 목록
| 분야 | 노트북 | 직접 확인하는 것 | 관련 자료 |
|---|---|---|---|
| 통계 | [lab01_sampling_bootstrap_pvalues](01_Statistics_Math/labs/lab01_sampling_bootstrap_pvalues.ipynb) | 표준오차, 신뢰구간 포함률, 부트스트랩, p-value 분포, FDR, Lasso | Efron 1979, ASA 2016, Benjamini–Hochberg 1995, Tibshirani 1996 |
| ML | [lab01_validation_leakage_metrics](02_Machine_Learning/labs/lab01_validation_leakage_metrics.ipynb) | 과적합, 교차검증, 데이터 누수 2종, 불균형 지표 | Domingos 2012, Kapoor & Narayanan 2022 |
| ML | [lab02_boosting_from_scratch_shap](02_Machine_Learning/labs/lab02_boosting_from_scratch_shap.ipynb) | 부스팅 직접 구현, 분할 이득 공식, 조기 종료, SHAP 가법성 | Friedman 2001, XGBoost, LightGBM, SHAP |
| DL | [lab01_backprop_from_scratch](03_Deep_Learning/labs/lab01_backprop_from_scratch.ipynb) | 스칼라 autograd → 행렬 역전파 → PyTorch 일치 | Rumelhart 1986, micrograd |
| DL | [lab02_training_dynamics](03_Deep_Learning/labs/lab02_training_dynamics.ipynb) | Adam 직접 구현, 학습률 민감도, 잔차 연결, 드롭아웃 | Adam, ResNet, Dropout, BatchNorm |
| LLM | [lab01_tokenizer_attention_from_scratch](04_NLP_LLM/labs/lab01_tokenizer_attention_from_scratch.ipynb) | BPE, 어텐션 식, √d_k, causal mask, 멀티헤드, 위치 인코딩 | BPE, Attention Is All You Need |
| LLM | [lab02_embeddings_retrieval_rag](04_NLP_LLM/labs/lab02_embeddings_retrieval_rag.ipynb) | 희소·밀집 검색, Recall@k, RAG, 검색/생성 오류 분리 | Sentence-BERT, DPR, RAG |
| LLM | [lab03_llm_eval_error_bars](04_NLP_LLM/labs/lab03_llm_eval_error_bars.ipynb) | 평가의 표준오차, 짝지은 비교, 군집 SE, BBQ 편향 점수 신뢰구간 | Adding Error Bars to Evals, BBQ |
| CV | [lab01_cnn_and_toy_diffusion](05_Computer_Vision/labs/lab01_cnn_and_toy_diffusion.ipynb) | 합성곱, 등변성과 불변성, 2차원 DDPM 학습·샘플링 | ResNet, ViT, DDPM |
| 추천 | [lab01_cf_mf_bpr](06_Recommender_Systems/labs/lab01_cf_mf_bpr.ipynb) | 인기도·item-kNN·BPR-MF, Recall/NDCG, 커버리지 | Amazon 2003, Koren 2009, BPR, Dacrema 2019 |
| 시계열 | [lab01_forecast_baselines_backtest](07_Time_Series/labs/lab01_forecast_baselines_backtest.ipynb) | 백테스트, MASE, ETS, LightGBM, Chronos-2 zero-shot | Hyndman & Koehler 2006, M5, Chronos-2 |
| 실험 | [lab01_ab_test_simulation](08_Causal_Inference_Experimentation/labs/lab01_ab_test_simulation.ipynb) | 검정력, peeking, always-valid p, CUPED, SRM | Kohavi 2009, Johari 2017, CUPED, Fabijan 2019 |
| 공개 모델 | [lab01_inspect_open_model](12_Open_Models/labs/lab01_inspect_open_model.ipynb) | config, 파라미터 수 손계산, 토큰→logits→샘플링, logit lens | SmolLM2 |
| 공개 모델 | [lab02_train_tiny_gpt_end_to_end](12_Open_Models/labs/lab02_train_tiny_gpt_end_to_end.ipynb) | 데이터→토크나이저→학습→가중치 저장→모델 카드 | nanoGPT |

모델을 내려받는 노트북: LLM lab02(약 1.5GB), 시계열 lab01의 6절(선택), 공개 모델 lab01(약 0.5GB). 나머지는 다운로드가 없다.

아직 없는 실습(09 SQL, 10 시각화, 08 관찰 데이터 인과추론, 공개 모델 체크포인트 비교·미세조정)은 각 폴더 `PRACTICE.md`의 과제로 대신한다.
