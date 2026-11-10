# 용어집 (Glossary)

논문에서 자주 만나는 용어. 자세한 설명은 연결된 문서 참고. 새 용어를 만나면 여기에 추가한다.

| 용어 | 한국어 | 한 줄 설명 | 문서 |
|---|---|---|---|
| ablation study | 제거 실험 | 구성요소를 하나씩 빼서 기여도를 확인 | [09](09_how-to-read-papers.md) |
| attention | 어텐션 | 다른 위치를 얼마나 참고할지 가중치로 섞는 연산 | [06](06_attention-transformer.md) |
| backpropagation | 역전파 | 연쇄법칙으로 기울기를 출력→입력 방향으로 계산 | [05](05_neural-networks.md) |
| baseline | 베이스라인 | 비교 기준이 되는 기존/단순 방법 | [04](04_ml-basics.md) |
| benchmark | 벤치마크 | 모델을 비교하기 위한 표준 데이터셋·과제 | [06](06_attention-transformer.md) |
| bias (통계) | 편향 | 추정치가 참값에서 체계적으로 벗어난 정도 | [04](04_ml-basics.md) |
| bias (공정성) | 편향 | 특정 집단에 대한 체계적인 불리함·고정관념 | 04_NLP_LLM의 BBQ 노트 |
| confidence interval | 신뢰구간 | 추정의 불확실성 범위 | [03](03_probability-statistics.md) |
| confounder | 교란변수 | 처치와 결과 모두에 영향을 주는 변수 | [07](07_causal-experiment-basics.md) |
| cross-entropy | 교차 엔트로피 | 분류의 표준 손실. 음의 로그우도 | [05](05_neural-networks.md) |
| cross-validation | 교차검증 | 분할을 바꿔 가며 반복 평가 | [04](04_ml-basics.md) |
| data leakage | 데이터 누수 | 예측 시점에 알 수 없는 정보가 학습에 포함 | [04](04_ml-basics.md) |
| embedding | 임베딩 | 대상(단어·사용자·이미지)을 나타내는 밀집 벡터 | [06](06_attention-transformer.md) |
| epoch | 에폭 | 전체 학습 데이터를 한 번 순회 | [02](02_calculus-optimization.md) |
| fine-tuning | 미세조정 | 사전학습 모델을 특정 과제에 추가 학습 | [06](06_attention-transformer.md) |
| generalization | 일반화 | 보지 못한 데이터에서도 잘 작동하는 것 | [04](04_ml-basics.md) |
| gradient | 그래디언트(기울기) | 손실을 가장 빠르게 증가시키는 방향 | [02](02_calculus-optimization.md) |
| ground truth | 정답 | 평가의 기준이 되는 실제 라벨 | [04](04_ml-basics.md) |
| hyperparameter | 하이퍼파라미터 | 학습 전에 사람이 정하는 설정값 | [04](04_ml-basics.md) |
| i.i.d. | 독립 동일 분포 | 표본들이 서로 독립이고 같은 분포에서 나옴 | [03](03_probability-statistics.md) |
| inductive bias | 귀납적 편향 | 모델 구조에 담긴 데이터에 대한 가정 | [05](05_neural-networks.md) |
| inference (ML) | 추론 | 학습된 모델로 예측하는 단계 | [05](05_neural-networks.md) |
| inference (통계) | 추론 | 표본으로 모집단에 대해 결론을 내림 | [03](03_probability-statistics.md) |
| logit | 로짓 | softmax/sigmoid를 거치기 전의 점수 | [05](05_neural-networks.md) |
| loss / objective | 손실 / 목적함수 | 최소화(최적화)하려는 값 | [02](02_calculus-optimization.md) |
| overfitting | 과적합 | 학습 데이터에만 지나치게 맞춰짐 | [04](04_ml-basics.md) |
| p-value | 유의확률 | 귀무가설이 참일 때 이만큼 극단적인 결과가 나올 확률 | [03](03_probability-statistics.md) |
| pre-training | 사전학습 | 대규모 데이터로 일반 표현을 먼저 학습 | [06](06_attention-transformer.md) |
| regularization | 정규화(규제) | 과적합을 막기 위한 제약 (L1/L2, dropout) | [02](02_calculus-optimization.md) |
| normalization | 정규화 | 값의 범위·분포를 맞춤 (BatchNorm, 표준화). 위와 다른 개념 | [05](05_neural-networks.md) |
| representation | 표현 | 모델이 입력을 내부적으로 나타낸 벡터 | [05](05_neural-networks.md) |
| SOTA | 최고 성능 | state-of-the-art. 현재까지 보고된 최고 결과 | [09](09_how-to-read-papers.md) |
| statistical power | 검정력 | 실제 효과가 있을 때 그것을 검출할 확률 | [03](03_probability-statistics.md) |
| token | 토큰 | 모델이 처리하는 텍스트의 최소 단위 | [06](06_attention-transformer.md) |
| treatment effect | 처치 효과 | 개입이 결과에 미친 인과적 영향 | [07](07_causal-experiment-basics.md) |
| zero-shot / few-shot | 제로샷 / 퓨샷 | 예시 없이 / 몇 개의 예시만으로 과제 수행 | [06](06_attention-transformer.md) |
