# CLAUDE.md

This file is automatically read by Claude Code.

---

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
```
### [Date] Title
- **Context**: What task was in progress
- **Problem**: What exactly went wrong
- **Cause**: Why it happened (write "unknown" if unclear)
- **Failed attempts**: Approaches tried that did NOT work
- **Fix**: How it was resolved
- **Verification**: How the fix was confirmed (command, screen, result)
- **Reuse condition**: When to refer back to this entry
- **Prevention**: How to avoid this next time
- **Tags**: #category
```

### Principles:
- Write entries concisely but with enough context to understand later.
- Copy error messages exactly as they appear.
- Never skip logging an error, even if it seems minor.
- If ErrorNote.md does not exist, create it at the project root before starting.
