# 도구 (Python · SQL · Git · 재현성)

## 왜 필요한가
논문을 "읽었다"와 "이해했다"의 차이는 **직접 돌려 보았는가**에서 난다. 또한 실무 데이터사이언티스트의 시간 대부분은 SQL로 데이터를 뽑고 pandas로 정리하는 데 쓰인다.

## 최소한 이것만
| 영역 | 알아야 할 것 | 확인 질문 |
|---|---|---|
| **SQL** | `SELECT/WHERE/GROUP BY/HAVING`, `JOIN`(inner/left), 서브쿼리·CTE(`WITH`), **윈도 함수**(`ROW_NUMBER`, `LAG`, `SUM() OVER`) | "사용자별 첫 구매일과 7일 내 재구매 여부"를 쿼리 하나로 쓸 수 있는가? |
| **Python** | 자료구조(list/dict), 함수, comprehension, 가상환경 | |
| **NumPy** | 배열, shape, 브로드캐스팅, 벡터화 | `for` 없이 행렬 연산을 쓸 수 있는가? |
| **pandas** | `groupby`, `merge`, `pivot`, 결측 처리, 날짜 처리 | SQL로 한 일을 pandas로도 할 수 있는가? |
| **시각화** | matplotlib / seaborn / plotly | 분포·관계·추세에 맞는 차트를 고를 수 있는가? |
| **scikit-learn** | `fit/predict`, `Pipeline`, `train_test_split`, `cross_val_score` | 전처리를 Pipeline 안에 넣어 누수를 막는가? → [ML 기초](04_ml-basics.md) |
| **PyTorch** | Tensor, autograd, `nn.Module`, DataLoader | → [신경망](05_neural-networks.md)의 학습 루프 |
| **Git** | `clone/add/commit/push`, branch, pull request | 이 저장소가 좋은 연습장이다 |
| **셸** | `cd/ls/grep`, 파이프, 환경변수 | |

## 재현성 (README 10번 질문: "결과를 재현할 수 있는가?")
- **랜덤 시드 고정**, 패키지 버전 기록 (`requirements.txt`, `uv`, `conda env export`)
- 데이터 버전과 전처리 코드를 함께 보관
- 노트북은 위에서 아래로 한 번에 실행되는지 확인 (셀 실행 순서 꼬임 주의)
- 실험 기록: 설정·지표·코드 커밋을 함께 (MLflow, Weights & Biases 등)

## 논문 코드 읽는 요령
1. README의 실행 명령부터 — 어떤 스크립트가 진입점인지.
2. 설정 파일(config)에서 하이퍼파라미터를 찾아 논문의 표와 대조.
3. `model.py`의 `forward()`를 논문의 그림·수식과 한 줄씩 대응.
4. 작은 데이터로 한 번 돌려 텐서 shape을 출력해 본다.
5. 공식 코드가 없으면 Hugging Face나 GitHub에서 제3자 구현을 찾는다.

## 더 공부할 자료
- SQL: [Mode SQL Tutorial](https://mode.com/sql-tutorial/)
- Python 분석: [Python Data Science Handbook](https://jakevdp.github.io/PythonDataScienceHandbook/) · [Kaggle Learn](https://www.kaggle.com/learn)
- 셸·Git: [The Missing Semester (MIT)](https://missing.csail.mit.edu/)
- 데이터 정리 원칙: [Tidy Data (Wickham, 2014)](https://doi.org/10.18637/jss.v059.i10)
