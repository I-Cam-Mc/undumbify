# Undumbify

Undumbify turns an underspecified request into a confirmed, copy-ready prompt without executing the underlying task.

It uses CLEAR:

- **C**onfirm intent
- **L**ocate relevant context
- **E**licit the highest-value decisions
- **A**lign requirements, evidence, and success criteria
- **R**eflect the target state and render the prompt

## Modes

| Invocation | Depth | Confirmation stops |
|---|---|---:|
| `/undumb` or `$undumbify min` | Minimum | 1 |
| `/undumbify` or `$undumbify` | Standard | 2 |
| `/undumbifyMAX` or `$undumbify max` | Maximum | Up to 3 |

All modes remain prompt-only. MAX means deeper clarification, not maximum model reasoning effort.

On first use, Undumbify proceeds with sensible defaults and offers its optional preference questionnaire after producing the first useful prompt. Setup does not consume a mode's confirmation budget.

## Install

Clone this repository into the Codex skills directory:

```bash
git clone https://github.com/I-Cam-Mc/undumbify.git ~/.codex/skills/undumbify
```

Codex can invoke the canonical skill as `$undumbify`. Slash aliases require corresponding routing instructions in the user's `AGENTS.md`.

## Design choices

- A short intent echo confirms the model's interpretation before detailed work.
- A target-state checksum is produced only after context, decisions, and assumptions are settled.
- Questions are capped and ranked by their expected effect on the result.
- Model effort is chosen independently from clarification depth.
- External skill discovery is allowed but bounded, with popularity and critical acclaim treated as secondary confidence signals.
- Unlazy remains a separate, exceptional completion workflow.
