# 전체 실습 지도 — 교수님 반복 업무, 클로드 코드로 덜어내기

| 실습 | 안내서 | 제목 | 시간 | 새로 익히는 클로드 코드 기능 | 실습 폴더 |
|---|---|---|---|---|---|
| ★ | `tutor/labs/express30.md` | 30분 핵심 코스 | 30분 | 작업실 확인, 작업 모드, 백업·계획·실행·검증, 허락 화면, 스킬 만들기 | `practice/04-submissions` |
| 0 | `tutor/labs/lab00-orientation.md` | 오리엔테이션 | 5분 | 대화 입력, `/` 명령, 실습 도우미 사용법 | (루트) |
| 1 | `tutor/labs/lab01-workspace.md` | 작업실 확인 | 10분 | 작업 폴더 개념, `!` 명령, Esc, Ctrl+C, `/clear` | (루트) |
| 2 | `tutor/labs/lab02-first-file.md` | 첫 파일 | 15분 | 허락 화면, `@파일`, 거절, `/rewind`, Shift+Tab 모드 | `practice/02-first-file` |
| 3 | `tutor/labs/lab03-folder-cleanup.md` | 폴더 정리 | 25분 | 계획 모드, `claude -c`, 폴더별 `CLAUDE.md` | `practice/03-folder-cleanup` |
| 4 | `tutor/labs/lab04-submissions.md` | 제출 현황표 | 20분 | 대조·표 만들기, 애매한 것 넘기기 | `practice/04-submissions` |
| 5 | `tutor/labs/lab05-notices.md` | 공지문 15개 | 15분 | 여러 파일 일괄 생성, `[확인 필요]` 원칙 | `practice/05-notices` |
| 6 | `tutor/labs/lab06-custom-command.md` | 나만의 명령 | 15분 | 스킬(`/명령`) 만들기, `$ARGUMENTS` | `.claude/skills/` |
| 7 | `tutor/labs/lab07-one-line.md` | 한 줄 자동화 | 10분 | `claude -p`, 결과를 파일로 저장 | `practice/04-submissions` |
| 8 | `tutor/labs/lab08-my-automation.md` | 내 업무 설계 | 10분 | 설계 시트 → 내 스킬 초안 | `practice/08-my-automation` |
| 보너스 | `tutor/labs/bonus.md` | B1~B4 | 각 10분 | 수업 후 혼자 해 보기 | `practice/bonus-*` |

## 수업 시간별 추천 경로 (강사용)

- **30분**: ★ 30분 핵심 코스 하나 (`/lab 30`). 실습 0~8은 수업 후 자습
- **60분**: 0 → 1 → 2 → 4 → 6 (실습 3·5·7·8은 과제로)
- **90분**: 0 → 1 → 2 → 3 → 4 → 6 → 8
- **120분**: 0 → 8 전체 (보너스는 수업 후 자습)

교수님이 "시간이 없어요"라고 하시면 위 경로를 제안하세요.

## 실습 흐름의 뼈대 (모든 실습에 반복됨)

**이동·확인 → 백업 → 계획 → 실행 → 검증 → 기록 → 근육 체크**

- 클로드 코드는 '실행'을 빠르게 해 줍니다.
- 백업·계획 검토·검증·근육 체크는 교수님의 판단입니다.
