---
name: reset-lab
description: 실습 재료를 처음 상태로 되돌립니다. 예) /reset-lab 3
argument-hint: "[실습 번호 2~8 또는 bonus]"
disable-model-invocation: true
---

# /reset-lab — 실습 재료 초기화

초기화할 실습: $ARGUMENTS

번호와 폴더의 짝:
- 2 → `practice/02-first-file`
- 3 → `practice/03-folder-cleanup`
- 4, 7 → `practice/04-submissions`
- 5 → `practice/05-notices`
- 8 → `practice/08-my-automation`
- bonus → `practice/bonus-1-meetings`, `practice/bonus-2-faq`, `practice/bonus-4-literature`
- 6 → 초기화할 재료 없음. 만든 스킬을 지우고 싶으면 `.claude/skills/weekly-notice` 폴더를 옮기면 된다고 안내.

순서:
1. 무엇을 할지 먼저 말씀드립니다: "지금 폴더는 지우지 않고 `practice/_old/폴더이름-날짜시각` 으로 옮겨 두고, 원본(`tutor/starter/`)을 새로 복사합니다."
2. 교수님이 좋다고 하시면 진행합니다. 지금 폴더를 `practice/_old/` 아래로 **옮기고**(삭제하지 않음), `tutor/starter/` 의 같은 폴더를 `practice/` 로 복사합니다.
3. 파일 개수로 원본과 같은지 확인하고 결과를 알려 드립니다.
4. `my-progress.md` 의 현재 위치를 그 실습의 STEP 1로 바꾸고, STEP 1을 다시 안내할지 여쭙니다.
