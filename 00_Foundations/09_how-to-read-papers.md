# 논문 읽는 법

루트 [README](../README.md)의 14개 질문에 답하기 위한 실전 절차.

> 이 문서는 **요약본**이다. 실제 논문(ResNet)으로 단계별 연습 문제를 풀고 싶다면 → [논문 읽기·정리·기억 훈련 워크북](10_paper-reading-workbook.md)

## 3단계 읽기 (Keshav, "How to Read a Paper")
| 단계 | 시간 | 읽는 부분 | 얻는 것 | README 질문 |
|---|---|---|---|---|
| 1차: 훑기 | 5~10분 | 제목, 초록, 서론 첫·끝 문단, 소제목, 그림·표, 결론 | 무엇을 왜 했는지, 계속 읽을 가치가 있는지 | 2, 3, 11 |
| 2차: 내용 파악 | 1시간 | 전체를 읽되 증명·세부 수식은 건너뜀. 그림과 표를 꼼꼼히 | 핵심 주장과 근거를 남에게 설명할 수 있음 | 1, 4~9, 12, 13 |
| 3차: 재구성 | 수 시간 | 저자와 같은 가정에서 내가 다시 만든다고 생각하며 | 숨은 가정·약점 발견, 재현 가능 | 10, 14 |

대부분의 논문은 1차로 충분하고, 필독 목록의 논문만 2차 이상으로 읽는다.

## 섹션별로 찾을 것
| 섹션 | 찾을 것 |
|---|---|
| Abstract | 문제 – 방법 – 결과 한 문장씩 |
| Introduction | 기존 방법의 한계(동기), 기여(contributions) 목록 |
| Related Work | 이 논문이 어느 흐름에 속하는가. 모르는 선행 연구는 메모만 해 둔다 |
| Method | 그림 1개와 핵심 수식 1~2개. 입력과 출력의 형태(shape) |
| Experiments | 데이터셋, 베이스라인, 지표, 주 결과 표, ablation |
| Discussion / Limitations | 저자가 인정한 한계 — 가장 정직한 부분 |
| Appendix | 하이퍼파라미터, 추가 실험. 재현할 때 필요 |

## 표와 그림 읽기
- 표: **굵은 글씨**가 최고 성능. 지표 옆 ↑/↓(높을수록/낮을수록 좋음)를 확인.
- 개선 폭이 오차(±)보다 큰가? 시드를 몇 번 돌렸는가? → [확률·통계](03_probability-statistics.md)
- 그래프: 축의 단위와 스케일(log 여부), y축이 0에서 시작하는지.
- Ablation 표: 어떤 구성요소가 성능에 실제로 기여했는지 알려 준다. 종종 가장 유익한 표.

## 비판적으로 읽기 위한 질문
1. 베이스라인은 공정한가? (같은 데이터·연산량·튜닝 노력) → [ML 기초](04_ml-basics.md)
2. 평가 데이터가 학습 데이터에 섞였을 가능성은? (특히 LLM 벤치마크)
3. 주장이 실험 범위를 넘어서지 않는가? (한 데이터셋 결과를 일반화)
4. 상관을 인과처럼 말하고 있지 않은가? → [인과·실험](07_causal-experiment-basics.md)
5. 이 방법이 실패하는 경우는 언제인가? 저자가 보여 주었는가?
6. 코드·데이터가 공개되어 있는가?

## 모르는 것이 나왔을 때
- 수식의 기호 → 논문의 Notation/Preliminaries 절, 없으면 [용어집](glossary.md).
- 개념 → 이 폴더의 해당 문서 → 그래도 모르면 질문하고 `qna.md`에 기록.
- 선행 연구 → 지금 읽지 말고 `references.md`에 적어 두고 본 논문을 끝낸다. (토끼굴 방지)

## 이 저장소의 정리 흐름
1. 분야 폴더의 `READING_LIST.md`에서 자료 선택 (★ 표시부터)
2. 같은 폴더의 `PRACTICE.md`에서 그 자료의 읽기 가이드 확인
3. `YYYY-MM-DD_주제-slug/` 폴더 생성 → `summary.md` (1차 읽기 메모 → 14개 질문)
4. `labs/`의 실습 노트북으로 핵심 주장 확인 → `summary.md`의 실습 기록
5. 궁금한 점을 대화 → `qna.md`에 누적, 다음에 읽을 것 → `references.md`
6. 기억 점검 질문으로 D+1 · D+7 · D+21 복습 → 복습 기록
7. `READING_LIST.md`의 상태를 ✅로

## 참고
- [How to Read a Paper (Keshav, 2007)](https://doi.org/10.1145/1273445.1273458)
- 🇰🇷 한국어 논문 리뷰 채널 — 원문을 읽기 전에 구조를 잡거나, 읽은 뒤 내 이해와 비교하는 용도: [PR12 딥러닝 논문읽기 모임](https://www.youtube.com/playlist?list=PL0oFI08O71gKjGhaWctTPvvM7_cVzsAtK) · [동빈나 꼼꼼한 딥러닝 논문 리뷰와 코드 실습](https://www.youtube.com/playlist?list=PLRx0vPvlEmdADpce8aoBhNnDaaHQN1Typ) · [DSBA 연구실 논문 리뷰 (예: ViT)](https://www.youtube.com/watch?v=0kgDve_vC1o) · [딥러닝논문읽기모임 (최신 논문, 예: DiT)](https://www.youtube.com/watch?v=B7_ht9TDtIE)
- 🇰🇷 영어 논문을 한국어 도움을 받아 읽는 요령: [KOREAN_START.md](../KOREAN_START.md)의 4절
