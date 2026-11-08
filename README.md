# 🧭 교수님을 위한 클로드 코드 실습실

**반복 업무, 클로드 코드 CLI로 덜어내기** — 필로소피 AI 교육

이 저장소를 내려받아 그 폴더에서 `claude` 를 실행하면, **실습 도우미**가 한 단계씩 안내해 드립니다.
교수님은 안내를 따라 입력하고, 결과를 직접 확인하시면 됩니다.

- ⏱ 30분~2시간 (**30분 핵심 코스** / 60분 / 90분 / 120분 경로 선택 가능)
- 대상: 터미널과 코딩이 처음인 교수님
- 모든 실습은 **가상 자료**(가상 학생 30명, 가상 강의자료)로 진행합니다

---

## ★ 시간이 30분뿐이라면 — 30분 핵심 코스

작은 연습은 건너뛰고, **교수님 업무 하나를 처음부터 끝까지** 맡겨 봅니다.
과제 제출물 27개를 가상 명단 30명과 대조해 현황표를 만들고, 그 일을 `/submission-check` 라는 나만의 명령으로 저장합니다.

| 단계 | 내용 | 익히는 것 |
|---|---|---|
| 1 | 작업실 확인과 작업 모드 | `! pwd`, Shift+Tab (기본 / 편집 자동 / 계획), Esc |
| 2 | 재료 보기와 백업 | `!` 로 내 손으로 백업하기 |
| 3~4 | 계획 모드로 계획 보고 고치기 | 실행 전에 계획부터, 경계 규칙 정해 주기 |
| 5 | 실행 | 허락 화면 읽기, 삭제는 거절하고 방향 바꾸기 |
| 6 | 검증 | 엑셀로 직접 열어 세어 보기, `확인해 주세요` |
| 7 | 나만의 명령 만들기 | 스킬(`.claude/skills/…/SKILL.md`), `$ARGUMENTS` |
| 8 | 근육 체크 | 맡길 일과 맡기지 않을 일 |

`/start` 에서 **1. 30분 핵심 코스**를 고르시거나, 언제든 `/lab 30` 을 입력하시면 됩니다. 안내서: `tutor/labs/express30.md`

---

## 오늘 하게 될 실습 (60분~2시간 과정)

| 실습 | 내용 | 교수님 업무로 치면 |
|---|---|---|
| 0 | 오리엔테이션 | 실습 도우미와 인사하기 |
| 1 | 작업실 확인 | "연구실 3번 책장만 정리해 줘" — 일할 방 정해 주기 |
| 2 | 첫 파일 | 수업 소개 파일 만들기 · 고치기 · 거절하기 · 되돌리기 |
| 3 | 폴더 정리 | 뒤죽박죽 강의자료 40개를 주차별로 정리 |
| 4 | 제출 현황표 | 과제 제출물 27개 ↔ 명단 30명 대조, 지각·미제출 확인 |
| 5 | 공지문 15개 | 강의계획서 한 장으로 15주 LMS 공지 초안 |
| 6 | 나만의 명령 | `/weekly-notice 3` 한 마디로 매주 공지 만들기 |
| 7 | 한 줄 자동화 | 터미널 한 줄로 미제출자 안내문 받기 |
| 8 | 내 업무 설계 | 내 실제 업무로 자동화 초안 만들어 가기 |
| 보너스 | 혼자 해 보기 | 회의록 정리 · 학생 질문 FAQ · 피드백 초안 · 문헌 정리표 |

---

## 시작하기 (3단계)

### 준비물
- 클로드 **유료 계정** (Pro · Max · Team · Enterprise, 또는 Console 계정. 무료 플랜은 안 됩니다)
- macOS 13 이상 / Windows 10 (1809) 이상, 인터넷

### ① 클로드 코드 설치 (수업 전에 미리 해 오시면 좋습니다)

터미널을 엽니다.
- **Mac**: ⌘ + Space → "터미널" → 엔터
- **Windows**: 시작 → "PowerShell" → 열기 (관리자 권한 필요 없음. 줄 앞에 `PS` 가 보이면 맞습니다)

아래 한 줄을 복사해 붙여넣고 엔터:

```bash
# Mac
curl -fsSL https://claude.ai/install.sh | bash
```
```powershell
# Windows (PowerShell)
irm https://claude.ai/install.ps1 | iex
```

설치가 끝나면 **터미널 창을 닫고 새로 연 뒤** 확인:
```
claude --version
```
숫자가 나오면 성공입니다. 처음 한 번은 `claude` 를 입력해 로그인해 두세요. (브라우저가 열리면 평소 쓰시는 클로드 계정으로 로그인 → `/exit` 로 종료)

> 막히시면: `claude doctor` 또는 공식 문서 https://code.claude.com/docs/en/install

### ② 실습실 내려받기

홈 폴더에 `claude-lab` 이라는 이름으로 받습니다. **아래 중 하나**만 하시면 됩니다.

**방법 A — 한 줄로 받기 (추천, Git 필요 없음)**

```powershell
# Windows (PowerShell)
cd ~; irm https://github.com/philosophyAIEDU/261107philosophy2/archive/refs/heads/main.zip -OutFile claude-lab.zip; Expand-Archive claude-lab.zip -DestinationPath .; Rename-Item 261107philosophy2-main claude-lab; Remove-Item claude-lab.zip
```
```bash
# Mac
cd ~ && curl -L -o claude-lab.zip https://github.com/philosophyAIEDU/261107philosophy2/archive/refs/heads/main.zip && ditto -x -k claude-lab.zip . && mv 261107philosophy2-main claude-lab && rm claude-lab.zip
```

**방법 B — Git 을 쓰신다면**
```
cd ~
git clone https://github.com/philosophyAIEDU/261107philosophy2.git claude-lab
```

**방법 C — 마우스로**
이 페이지 위쪽 초록색 **Code** 버튼 → **Download ZIP** → 압축 풀기 → 폴더 이름을 `claude-lab` 으로 바꿔서 **홈 폴더**(Windows `C:\Users\내이름`, Mac `/Users/내이름`)로 옮기기.

### ③ 실습실에서 클로드 코드 실행

★ 클로드 코드 실행 3단계 습관 — **이동 → 확인 → 실행**

```
cd ~/claude-lab
pwd
claude
```

1. `pwd` 결과의 끝이 `claude-lab` 인지 확인하세요.
2. "이 폴더를 신뢰하나요?" 라고 물으면 **예(Yes)** 를 고릅니다.
3. 입력 칸에 아래를 입력하면 실습이 시작됩니다.

```
/start
```

---

## 실습 중에 쓰는 말 네 마디

| 이렇게 입력 | 이렇게 됩니다 |
|---|---|
| `다음` | 다음 단계로 |
| `힌트` | 막혔을 때 실마리 (정답 대신 힌트부터) |
| `확인해 주세요` | 실습 도우미가 실제 파일을 보고 잘 됐는지 확인 |
| `어디까지 했죠?` | 진도표 보기 |

그 밖에: `/lab 3` (3번 실습으로 바로 가기), `/lab 30` (30분 핵심 코스), `/stuck` (오류가 났을 때), `/reset-lab 3` (3번 실습 재료를 처음 상태로)

**진도는 자동으로 저장됩니다.** 중간에 꺼도 다시 `cd ~/claude-lab` → `claude` 하시면 이어서 할 수 있어요.

---

## 폴더 안내

```
claude-lab/
├── README.md            ← 지금 이 안내
├── CLAUDE.md            ← 실습 도우미의 업무 매뉴얼 (클로드가 자동으로 읽음)
├── .claude/skills/      ← /start, /next, /hint … 실습 도우미 명령 (실습 6에서 직접 만들어 봄)
├── practice/            ← ✏️ 교수님이 실습하는 곳 (가상 자료)
│   ├── 02-first-file/
│   ├── 03-folder-cleanup/   뒤죽박죽 강의자료 40개
│   ├── 04-submissions/      가상 명단 30명 + 과제 제출물
│   ├── 05-notices/          가상 강의계획서
│   ├── 08-my-automation/
│   └── bonus-*/             회의록, 학생 질문, 문헌 메모
├── tutor/               ← 실습 안내서 (사람이 읽어도 되는 교재)
│   ├── labs/            ← 30분 핵심 코스(express30.md), 실습 0~8, 보너스 안내서
│   ├── troubleshooting.md
│   └── starter/         ← 실습 재료 원본 (초기화용, 건드리지 않기)
└── instructor/          ← 강사용 진행 가이드
```

실습 안내서(`tutor/labs/`)는 그냥 읽어도 되는 교재입니다. 인쇄해서 옆에 두셔도 좋습니다.

---

## 꼭 지켜 주세요

- 실습은 **이 폴더(`claude-lab`) 안에서만** 합니다.
- 실제 학생 이름·학번·성적이 담긴 파일은 넣지 마세요. 실제 업무에 적용하실 때는 **소속 대학의 AI 활용 지침과 개인정보 규정**을 먼저 확인해 주세요.
- 클로드 코드는 내 파일을 **실제로** 바꿉니다. 실제 폴더에 적용할 때는 언제나 **백업 → 계획 → 실행 → 검증**.

> "도구는 클로드 코드, 판단은 교수님. 도구는 계속 바뀌어도, 생각하는 근육은 남습니다." — 필로소피 AI 교육

참고 문서 (공식): [설치](https://code.claude.com/docs/en/install) · [작업 모드](https://code.claude.com/docs/en/permission-modes) · [스킬](https://code.claude.com/docs/en/skills) · [한 줄 실행](https://code.claude.com/docs/en/headless)
