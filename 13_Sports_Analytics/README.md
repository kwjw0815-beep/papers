# Sports_Analytics

**범위:** 스포츠 데이터 분석 — 선수 추적(tracking) 데이터, 움직임 지표(스프린트·방향 전환), 선수 평가·스카우팅, 성과 예측, 대회형 분석(NFL Big Data Bowl 등)을 가설 → 검증 흐름으로 정리

📚 **[필독 자료 목록 (READING_LIST.md)](READING_LIST.md)** — 논문 52개 + 다른 폴더 소관 방법론 12개 (★ 코어, 🆕 2025~2026 자료 표시) · 선수 지식은 [00_Foundations](../00_Foundations)

## 정리 목록
| 날짜 | 주제 | 자료 유형 | 폴더 |
|---|---|---|---|

## 이 폴더를 쓰는 방법
- 스포츠 분석 논문·블로그·영상을 정리할 때 [CLAUDE.md](../CLAUDE.md)의 작업 흐름(`YYYY-MM-DD_주제-slug/` 아래 `summary.md`, `qna.md`, `references.md`)을 그대로 따른다.
- 통계·검증·인과의 일반 방법론 자료는 각자의 분야 폴더에 두고 여기에는 링크만 남긴다. 예: 부트스트랩·다중검정은 [01_Statistics_Math](../01_Statistics_Math), 데이터 누수·SHAP은 [02_Machine_Learning](../02_Machine_Learning), 교란·관찰 데이터 인과추론은 [08_Causal_Inference_Experimentation](../08_Causal_Inference_Experimentation). 스포츠 **도메인**에 특화된 자료(트래킹 지표, 선수 평가 모형, 스카우팅 연구)가 이 폴더의 대상이다.
- 자료가 어떤 프로젝트 가설의 근거로 쓰였는지는 그 노트 `summary.md` 맨 아래 `## 가설 연결` 표에 적는다. 가설 카드 쪽에도 이 노트 경로를 적어 **양방향**으로 연결한다.

## 연결된 프로젝트
| 프로젝트 | 가설 카드 | 연결 방식 |
|---|---|---|
| NFL Big Data Bowl 2027 (컴바인 트래킹 → 정규시즌 성과) | 프로젝트 저장소 `hypotheses/H###_*.md` | 카드 front-matter `papers:`에 이 폴더의 노트 경로, 노트 `## 가설 연결`에 H### |

READING_LIST의 DOI는 모두 OpenAlex·Crossref API로 존재와 서지를 확인했다(2026-11-24).
