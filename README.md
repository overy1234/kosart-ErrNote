# ErrorNote — AI Error Prevention System

> **Works with Claude Code · OpenAI Codex CLI · Any AI Agent**

---

## Why ErrorNote?

The biggest waste of tokens and time when coding with AI is **repeating the same mistakes**.

```
First mistake → AI fixes it → Same mistake again → Fix again → ...
```

As conversations grow longer, AI tends to forget earlier problems.  
In a new conversation, that context is gone entirely.  
ErrorNote solves this structural problem.

**By logging errors to a file**, the AI reads it before starting any task,  
understands what went wrong before, and avoids those mistakes from the start.

---

## Token Savings

| Situation | Without ErrorNote | With ErrorNote |
|-----------|------------------|----------------|
| Same error recurs | Re-diagnose & fix every time | Reference log → avoid immediately |
| Long debug loops | Massive token consumption | Prevented before they start |
| New conversation | Zero context | Error history shared instantly |
| Final review | Uncertain if mistakes were made | Checklist confirmation |

Preventing just 2–3 repeated mistakes can save thousands of tokens.

---

## Why It Makes You Faster

The biggest change I noticed from using ErrorNote with AI Agents is **speed**.

When errors stop repeating, the following disappear:

- Time spent re-explaining the same problem
- Time the AI spends re-diagnosing the root cause
- Time wasted retrying solutions that already failed
- Time lost rolling back and starting over

```
[Without ErrorNote]
Problem → Explain → Diagnose → Try → Fail → Explain again → ...  (slow)

[With ErrorNote]
Problem → AI reads log → Goes straight to the right solution  (fast)
```

As error records accumulate, the AI picks the correct approach from the start  
and reaches the goal in a straight line — no unnecessary trial and error.

> Saving tokens and going faster are the same principle.  
> **Fewer repeated errors → shorter conversations → faster completion.**

---

## File Structure

```
project root/
├── CLAUDE.md           ← Auto-read by Claude Code
├── AGENTS.md           ← Auto-read by OpenAI Codex CLI
├── ErrorNote.md        ← The actual error log (AI reads and writes this)
└── ErrorNote_prompt.md ← Copy-paste system prompt for other AI tools
```

---

## How It Works

```
Task starts
    │
    ▼
Read ErrorNote.md
    │
    ├─ Related error pattern found → proactively avoid it
    │
    ▼
Error occurs during task
    │
    ▼
Immediately append to ErrorNote.md
    │
    ▼
Task complete
    │
    ▼
Re-read ErrorNote.md → final check that no recorded mistakes were repeated
```

---

## How to Use

### 1. Claude Code

`CLAUDE.md` is already included. Just copy it to your project.

```bash
# Clone this repo, or copy just two files
CLAUDE.md       → add to your project root (or merge into existing CLAUDE.md)
ErrorNote.md    → add to your project root
```

Claude Code reads `CLAUDE.md` automatically at the start of every conversation — no extra setup needed.

---

### 2. OpenAI Codex CLI

`AGENTS.md` is already included. Copy it to your project root the same way.

```bash
AGENTS.md       → add to your project root
ErrorNote.md    → add to your project root
```

---

### 3. Other AI Agents / Chatbots

Copy the system prompt from `ErrorNote_prompt.md` and paste it into your AI tool.

| Platform | Where to paste |
|----------|---------------|
| ChatGPT Custom GPT | System Instructions |
| Cursor | `.cursorrules` or Rules for AI |
| Windsurf | Global Rules |
| Custom Agent | Top of the system prompt |

---

## Error Log Format

```markdown
### [2026-06-28] File path error
- **Context**: Creating a Unity script
- **Problem**: File was created outside Assets/ due to absolute path usage
- **Cause**: Passed the path directly to the MCP tool without validation
- **Fix**: Switched to relative path based on Assets/
- **Prevention**: Always verify the path is inside Assets/ before creating files
- **Tags**: #unity #filepath
```

---

## Principles

- Log every error, no matter how minor
- Copy error messages exactly as they appear
- Never delete resolved entries — mark them `[RESOLVED]` instead
- If a similar error recurs, add a recurrence note to the existing entry rather than creating a duplicate
- Never log sensitive information (API keys, passwords, etc.)

---

## Quick Start

```bash
git clone https://github.com/overy1234/kosart-ErrNote.git
```

Copy only the files you need into your project:

| AI Tool | Files to copy |
|---------|--------------|
| Claude Code | `CLAUDE.md` + `ErrorNote.md` |
| OpenAI Codex CLI | `AGENTS.md` + `ErrorNote.md` |
| Other Agent | paste prompt from `ErrorNote_prompt.md` + `ErrorNote.md` |

---

---

# ErrorNote — AI 에러 누적 방지 시스템

> **Claude Code · OpenAI Codex CLI · 기타 AI Agent 공통 적용 가능**

---

## 왜 ErrorNote인가?

AI와 함께 코딩할 때 가장 많은 토큰과 시간을 낭비하는 구간은 **같은 실수를 반복하는 순간**입니다.

```
첫 번째 실수 → AI가 고침 → 같은 실수 재발 → 다시 고침 → ...
```

AI는 대화가 길어질수록 앞서 겪은 문제를 잊거나, 새 대화에서는 그 맥락 자체가 없습니다.  
ErrorNote는 이 구조적 문제를 해결합니다.

**에러를 파일에 기록해두면**, AI는 작업 시작 전에 그 파일을 읽고  
이전에 어떤 실수가 있었는지 미리 파악한 뒤 작업을 시작합니다.

---

## 토큰 절약 효과

| 상황 | ErrorNote 없음 | ErrorNote 있음 |
|------|---------------|---------------|
| 같은 에러 재발 | 매번 새로 진단 · 수정 | 기록 참조 → 즉시 회피 |
| 긴 디버깅 루프 | 토큰 대량 소모 | 사전 방지로 루프 단축 |
| 새 대화 시작 | 맥락 0에서 시작 | 에러 이력 즉시 공유 |
| 작업 완료 검토 | 실수 여부 불확실 | 체크리스트로 재확인 |

같은 패턴의 실수를 2~3번만 방지해도 수천 토큰을 절약할 수 있습니다.

---

## 속도가 빨라지는 이유

AI Agent를 실제로 사용하면서 느낀 가장 큰 변화는 **작업 속도**입니다.

오류가 반복되지 않으면 다음이 사라집니다:

- 같은 문제를 다시 설명하는 시간
- AI가 원인을 다시 파악하는 시간
- 이미 시도했던 해결책을 또 시도하는 시간
- 실패 후 롤백하고 재시도하는 시간

```
[ErrorNote 없을 때]
문제 발생 → 설명 → 진단 → 시도 → 실패 → 다시 설명 → ...  (느림)

[ErrorNote 있을 때]
문제 발생 → AI가 기록 참조 → 바로 올바른 방향으로 진행  (빠름)
```

에러 기록이 쌓일수록 AI는 처음부터 올바른 접근을 선택하고,  
불필요한 시행착오 없이 목표 지점까지 직선으로 도달합니다.

> 토큰을 아끼는 것과 속도가 빨라지는 것은 같은 원리입니다.  
> **반복되는 오류가 줄면 → 대화가 짧아지고 → 그만큼 빠르게 완료됩니다.**

---

## 파일 구성

```
프로젝트 루트/
├── CLAUDE.md           ← Claude Code가 자동으로 읽는 지시 파일
├── AGENTS.md           ← OpenAI Codex CLI가 자동으로 읽는 지시 파일
├── ErrorNote.md        ← 실제 에러 기록 파일 (AI가 읽고 씀)
└── ErrorNote_prompt.md ← 다른 AI에 붙여넣기용 시스템 프롬프트
```

---

## 동작 방식

```
작업 시작
    │
    ▼
ErrorNote.md 읽기
    │
    ├─ 관련 에러 패턴 발견 → 선제적으로 회피하며 작업
    │
    ▼
작업 진행 중 에러 발생
    │
    ▼
즉시 ErrorNote.md에 기록
    │
    ▼
작업 완료
    │
    ▼
ErrorNote.md 재확인 → 같은 실수 없었는지 최종 체크
```

---

## 사용법

### 1. Claude Code

`CLAUDE.md`가 이미 포함되어 있습니다. 프로젝트에 복사하면 바로 적용됩니다.

```bash
# 이 저장소를 클론하거나, 파일 두 개만 복사
CLAUDE.md       → 본인 프로젝트 루트에 추가 (또는 기존 CLAUDE.md에 내용 병합)
ErrorNote.md    → 본인 프로젝트 루트에 추가
```

Claude Code는 대화 시작 시 `CLAUDE.md`를 자동으로 읽으므로 별도 설정이 필요 없습니다.

---

### 2. OpenAI Codex CLI

`AGENTS.md`가 이미 포함되어 있습니다. 동일하게 프로젝트 루트에 복사합니다.

```bash
AGENTS.md       → 본인 프로젝트 루트에 추가
ErrorNote.md    → 본인 프로젝트 루트에 추가
```

---

### 3. 기타 AI Agent / 챗봇

`ErrorNote_prompt.md` 안의 시스템 프롬프트를 복사해서 붙여넣으세요.

| 플랫폼 | 붙여넣을 위치 |
|--------|-------------|
| ChatGPT Custom GPT | System Instructions |
| Cursor | `.cursorrules` 또는 Rules for AI |
| Windsurf | Global Rules |
| 직접 구현한 Agent | system prompt 최상단 |

---

## ErrorNote.md 에러 기록 형식

```markdown
### [2026-06-28] 파일 경로 오류
- **상황**: Unity 스크립트 생성 중
- **문제**: 절대 경로를 사용해 파일이 Assets 외부에 생성됨
- **원인**: MCP 도구에 경로를 그대로 전달
- **해결**: `Assets/` 기준 상대 경로로 변경
- **재발 방지**: 파일 생성 전 항상 경로가 Assets/ 내부인지 확인
- **태그**: #unity #파일경로
```

---

## 원칙

- 에러가 아무리 사소해도 기록한다
- 에러 메시지는 원문 그대로 복사한다
- 해결된 항목은 삭제하지 않고 `[해결됨]` 태그를 붙여 유지한다
- 비슷한 에러가 재발하면 새 항목을 만들지 않고 기존 항목에 재발 메모를 추가한다
- API 키, 비밀번호 등 민감 정보는 절대 기록하지 않는다

---

## 빠른 시작

```bash
git clone https://github.com/overy1234/kosart-ErrNote.git
```

필요한 파일만 본인 프로젝트에 복사하세요:

| 사용 AI | 복사할 파일 |
|---------|-----------|
| Claude Code | `CLAUDE.md` + `ErrorNote.md` |
| OpenAI Codex CLI | `AGENTS.md` + `ErrorNote.md` |
| 기타 Agent | `ErrorNote_prompt.md` 내 프롬프트 복사 + `ErrorNote.md` |

---

## License

MIT
