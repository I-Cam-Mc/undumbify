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

## Designed for GPT-6 Astra

Undumbify was designed around GPT-6 Astra's documented behaviour. Astra is more likely to ask focused questions when an answer could change the outcome, follows skill instructions more strongly than earlier models, and can be more sensitive to unclear or conflicting guidance in skills and `AGENTS.md`. It also tends towards detailed, formatted responses and broad verification unless the desired scope is explicit. See OpenAI's [GPT-6 Astra model guidance](https://developers.openai.com/api/docs/guides/latest-model).

CLEAR turns those characteristics into a predictable prompt-scoping workflow:

- The intent echo makes Astra's interpretation visible before deeper work begins.
- Question and stop budgets keep useful clarification from becoming ceremony.
- Progressive disclosure reduces instruction conflicts and loads MAX-only guidance only when selected.
- Evidence, complexity, and stopping budgets guard against unnecessary detail and verification.
- Reasoning effort is chosen from the residual difficulty after scoping, independently of MIN, STANDARD, or MAX depth.

Astra supports Low, Medium, High, XHigh, and Max reasoning effort. Undumbify normally starts from the lowest level likely to satisfy the confirmed target state and escalates only for a specific reason. `/undumbifyMAX` means maximum clarification depth, not automatic Max reasoning. See the official [GPT-6 Astra model specification](https://developers.openai.com/api/docs/models/gpt-6-astra).

Astra is the primary design target, but the workflow remains usable with other capable instruction-following models.

## Install

Clone this repository into the Codex skills directory:

```bash
git clone https://github.com/I-Cam-Mc/undumbify.git ~/.codex/skills/undumbify
```

Codex can invoke the canonical skill as `$undumbify`. Slash aliases require corresponding routing instructions in the user's `AGENTS.md`.

Add this under the deliberate modes section of `~/.codex/AGENTS.md`:

```markdown
### `/undumb`, `/undumbify`, and `/undumbifyMAX`

Treat these commands as explicit invocations of the installed `undumbify` skill:

- `/undumb` selects MIN.
- `/undumbify` selects STANDARD.
- `/undumbifyMAX` selects MAX.
- `/upgrade` is an optional legacy alias for STANDARD.
```

## Design choices

- A short intent echo confirms the model's interpretation before detailed work.
- A target-state checksum is produced only after context, decisions, and assumptions are settled.
- Questions are capped and ranked by their expected effect on the result.
- Model effort is chosen independently from clarification depth.
- External skill discovery is allowed but bounded, with popularity and critical acclaim treated as secondary confidence signals.
- Unlazy remains a separate, exceptional completion workflow.
