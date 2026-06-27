# ErrorNote System Prompt
> Claude Code (CLAUDE.md) / OpenAI Codex / Hermes Agent 공통 사용 가능

---

## [SYSTEM PROMPT - 복사해서 붙여넣기]

```
## ErrorNote Rule

You must manage an ErrorNote.md file throughout all tasks.

### On task start:
- Read ErrorNote.md before beginning any work.
- If a related error or pattern exists, apply it proactively to avoid repeating the same mistake.

### During task:
- If an error, unexpected behavior, or problem occurs, immediately append it to ErrorNote.md using the format below.
- If the same or similar issue has been recorded before, add a recurrence note to the existing entry instead of creating a duplicate.

### On task completion (final review):
- Before finishing, re-read all entries in ErrorNote.md.
- Verify that none of the recorded mistakes were repeated in the current task.
- Mark resolved issues with [RESOLVED] — do not delete them.
- Add any newly discovered patterns to the "prevention" field.

### Entry format:
---
### [Date] Title
- **Context**: What task was in progress
- **Problem**: What exactly went wrong
- **Cause**: Why it happened (write "unknown" if unclear)
- **Fix**: How it was resolved
- **Prevention**: How to avoid this next time
- **Tags**: #category
---

### Principles:
- Write entries concisely but with enough context to understand later.
- Copy error messages exactly as they appear.
- Never skip logging an error, even if it seems minor.
```

---

## 적용 방법

| 플랫폼 | 적용 위치 |
|--------|-----------|
| **Claude Code** | 프로젝트 루트 `CLAUDE.md`에 붙여넣기 |
| **OpenAI Codex** | Custom instructions 또는 system prompt에 붙여넣기 |
| **Hermes Agent** | system prompt 또는 `<|im_start|>system` 블록에 붙여넣기 |
| **기타 Agent** | system prompt 최상단에 붙여넣기 |

---

## 주의사항

- `ErrorNote.md` 파일이 프로젝트에 없으면 AI가 새로 생성하도록 첫 줄에 추가 가능:
  ```
  If ErrorNote.md does not exist, create it at the project root before starting.
  ```
- 민감한 정보(API 키, 비밀번호 등)는 ErrorNote.md에 기록하지 않도록 주의.
