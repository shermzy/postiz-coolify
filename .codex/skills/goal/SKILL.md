---
name: goal
description: Use when the user invokes /goal or asks Codex to clarify, restate, track, or align on the current objective, success criteria, constraints, assumptions, and next action before continuing work.
metadata:
  short-description: Clarify the active goal
---

# Goal Alignment

Use this skill to turn the current conversation and workspace context into a concise operating target.

## Output

Respond with:

```markdown
**Goal**
<one sentence describing the concrete outcome>

**Constraints**
- <hard instruction, scope boundary, credential/source-of-truth rule, or risk>

**Done Means**
- <observable completion criterion>

**Next Step**
<the immediate action Codex should take>
```

## Rules

- Prefer concrete artifacts, paths, URLs, commands, and user-provided wording over generic restatements.
- Include assumptions only when they affect execution. Label them as assumptions.
- If the goal is ambiguous, state the best current interpretation and the one blocking question.
- Preserve explicit user instructions from `AGENTS.md`, repo docs, and the latest user message.
- Do not perform unrelated discovery while answering `/goal`; keep it to alignment unless the user asks to continue immediately.
