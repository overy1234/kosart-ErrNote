# ErrorNote System Prompt
> Claude Code (CLAUDE.md) / OpenAI Codex (AGENTS.md) / Hermes Agent 공통 사용 가능

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
- **Failed attempts**: Approaches tried that did NOT work (prevents repeating them)
- **Fix**: How it was resolved
- **Verification**: How the fix was confirmed (command, screen, result)
- **Reuse condition**: When to refer back to this entry
- **Prevention**: How to avoid this next time
- **Tags**: #category
---

### What to log:
- Errors likely to recur
- Problems that took a long time to diagnose
- Confusing console/UI behavior
- Build, deploy, or verification issues
- Project-specific rules

### What NOT to log:
- Simple typos
- Temporary network errors
- One-time external service outages
- Low-recurrence one-off issues
- Session progress notes (keep those in a separate summary)

### Security rules — NEVER log:
- API keys, OAuth tokens, session IDs
- .env values
- URLs containing tokens
- Passwords or credentials
- Production server addresses

### Principles:
- Write entries concisely but with enough context to understand later.
- Copy error messages exactly as they appear.
- Never skip logging an error, even if it seems minor.
- If ErrorNote.md does not exist, create it at the project root before starting.
```

---

## 적용 방법

| 플랫폼 | 적용 위치 |
|--------|-----------|
| **Claude Code** | 프로젝트 루트 `CLAUDE.md`에 붙여넣기 |
| **OpenAI Codex CLI** | 프로젝트 루트 `AGENTS.md`에 붙여넣기 |
| **Hermes Agent** | system prompt 또는 `<\|im_start\|>system` 블록에 붙여넣기 |
| **Cursor** | `.cursorrules` 또는 Rules for AI에 붙여넣기 |
| **기타 Agent** | system prompt 최상단에 붙여넣기 |

---

## Hermes Agent 전용 추가 규칙

Hermes를 사용하는 경우 아래 내용을 system prompt에 추가하세요:

```
## Hermes ErrorNote Rules

- If ErrorNote.md exists in the project root, read it before starting any task.
- During file operations, console submissions, or external service tasks — log any issue immediately.
- Before completing a task, re-read ErrorNote and confirm no recorded mistake was repeated.
- Do NOT log temporary session progress to ErrorNote — only log recurring, reusable error patterns.
- Distinguish between "session notes" (temporary) and "error patterns" (recurring) — only the latter belongs in ErrorNote.
```
