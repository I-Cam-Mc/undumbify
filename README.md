# /undumbify, /undumb and /undumbifymax - for using 5.6 & Astra on low-med-high without it being dumb

## Want consistently strong results from GPT-5.6 and Astra without defaulting to XHigh or Max?

Low, Medium and High can produce excellent work, but not reliably from an ordinary one-shot request. The model may under-scope the task, skip important context or evidence, stop at the first plausible answer, or compensate with unnecessary complexity.

![The same raw request with and without Undumbify](assets/undumbify-before-after.svg)

Undumbify scopes and confirms the work before execution. It tells you what the model understood, asks only the questions likely to change the result, makes assumptions inspectable, scopes the evidence and stopping point, and returns a copy-ready prompt. It never executes the underlying task.

The aim is simple: **use the most intelligent model at the lowest reasoning effort likely to do the job properly, and know why.**

## Pick the smallest version that will do the job

### `/undumb`

The fast version for a prompt that is mostly clear but would benefit from one check before you send it.

It gives you:

- one confirmation stop;
- a short paragraph explaining what it thinks you mean;
- up to two questions that could materially change the result;
- up to two consequential assumptions; and
- a lean final prompt, normally 150 to 300 words.

It does not run broad research or external skill discovery. It can flag an obvious capability gap.

**Use it for:** small builds, rewrites, focused research, straightforward decisions, or prompts where the main risk is one ambiguous interpretation.

**Recommended effort:** Low on GPT-5.6 Sol or GPT-6 Astra.

```text
/undumb Make the homepage positioning clearer without redesigning the site
```

### `/undumbify`

The default version for substantive work.

It gives you:

- two confirmation stops;
- a separate intent readback before detailed questions;
- bounded read-only context or memory retrieval when it could change the prompt;
- up to five high-value questions;
- visible assumptions and proposed success checks;
- a short description of the agreed end state; and
- one self-contained prompt with evidence, scope, authority, output, acceptance, and stopping requirements.

It may conduct bounded external skill discovery when a specialised capability could materially improve the task. It is not limited to installed skills.

**Use it for:** serious research, product decisions, implementation briefs, business writing, technical work, or anything you would be annoyed to rerun because the model interpreted it incorrectly.

**Recommended effort:** Low by default, Medium when meaningful ambiguity, research, or interacting constraints remain.

```text
/undumbify Work out whether we should replace first-line customer support with AI
```

### `/undumbifyMAX`

The deeper version for work where getting the framing wrong is expensive.

It gives you up to three confirmation stops and can add:

- deeper read-only context, source, and memory discovery;
- an explicit alignment packet covering assumptions, evidence, non-goals, success checks, and the complexity budget;
- relevant examples, inspiration, tools, resources, and failure modes;
- human or practitioner perspectives when lived experience and operational plausibility matter;
- supporting and dissenting evidence rather than one internally coherent story;
- external skill discovery across installed capabilities, trusted catalogues, registries, GitHub, and the wider web; and
- a separate end-state confirmation before the final prompt is written.

External skills are assessed on fit, instruction quality, trust, maintenance, testability, popularity, and independent critical acclaim. Nothing is installed or executed automatically.

**Use it for:** consequential strategy, high-stakes research, cross-domain systems, unfamiliar problem spaces, major architecture, or prompts that need real evidence and explicit trade-offs.

**Recommended effort:** Medium by default, High for genuinely difficult synthesis or verification. XHigh or Max should be exceptional and justified by the eventual task, not by the word MAX in the command.

```text
/undumbifyMAX Design how our consultancy should choose models, tools and external skills across different types of work
```

## Why it is designed this way

### Meaning comes before wording

Making a prompt longer is useless if the model misunderstood the objective. Undumbify starts with a compact readback so you can correct meaning before it optimises instructions around the wrong interpretation.

### Questions have to pay for themselves

Models often ask no questions unless forced, then ask filler when given a quota. Undumbify caps the number and only asks when plausible answers would change the outcome, method, evidence, scope, format, success criteria, tools, or recommended effort.

### Assumptions should be inspectable

User-stated, inferred, suggested, and confirmed requirements are treated differently. Suggested ideas do not silently become requirements. Consequential assumptions are labelled so you can answer yes, no, maybe, or replace them.

### Extra reasoning is not automatically extra judgement

Higher effort can produce more iterations, more verification, and more complexity. That is valuable when the task warrants it and wasteful when it does not. Undumbify scopes the problem first, then recommends Low, Medium, or High from the difficulty that remains.

### Reality has to interrupt internal coherence

For judgement-heavy work, MAX can seek real practitioner experience, corroborating and dissenting views, base rates, and evidence that would change the conclusion. Anecdote, expert judgement, empirical evidence, and model inference remain visibly different things.

### Complexity needs a job

Every extra source, tool, framework, skill, section, or step must satisfy a confirmed requirement or prevent a named failure. Otherwise it comes out. The prompt defines what good enough means and when to stop.

## Designed for GPT-5.6 Sol and GPT-6 Astra

OpenAI's [GPT-6 Astra model guidance](https://developers.openai.com/api/docs/guides/latest-model) says Astra is more likely to ask focused questions when additional input could change the result, follows skill instructions more strongly, and can be more sensitive to unclear or conflicting guidance in skills and `AGENTS.md`. It also tends towards detailed, formatted responses and broad verification unless the desired scope is explicit.

Undumbify uses those characteristics deliberately:

- the readback makes the model's interpretation visible;
- question and stop budgets contain unnecessary clarification;
- progressive disclosure avoids loading MAX instructions into small tasks;
- evidence and complexity budgets contain unnecessary elaboration; and
- reasoning effort stays independent from clarification depth.

Astra supports Low, Medium, High, XHigh, and Max reasoning effort. Undumbify normally starts from the lowest level likely to satisfy the confirmed target state and escalates for a specific reason. See the official [GPT-6 Astra model specification](https://developers.openai.com/api/docs/models/gpt-6-astra).

Astra is the primary design target. The workflow also works with GPT-5.6 Sol and other capable instruction-following models.

## What you get at the end

- A recommended model and reasoning effort, with a short explanation.
- A visible statement of the intended end state when the selected mode needs one.
- Consequential assumptions that still need to remain visible.
- One copy-ready prompt.
- A brief fit assessment covering clarity, evidence, scope control, and remaining risk.
- A simple yes or no choice for another clarification round.

On first use, Undumbify proceeds with sensible defaults and offers its optional preference questionnaire after producing the first useful prompt. Setup does not consume a mode's confirmation budget.

Unlazy is deliberately separate. Undumbify will only offer it when the eventual task has several independently verifiable obligations and partial completion could plausibly look successful.

## Install

Clone the repository into your Codex skills directory:

```bash
git clone https://github.com/I-Cam-Mc/undumbify.git ~/.codex/skills/undumbify
```

The canonical Codex invocation is `$undumbify`. To use the slash commands, add this under the deliberate modes section of `~/.codex/AGENTS.md`:

```markdown
### `/undumb`, `/undumbify`, and `/undumbifyMAX`

Treat these commands as explicit invocations of the installed `undumbify` skill:

- `/undumb` selects MIN.
- `/undumbify` selects STANDARD.
- `/undumbifyMAX` selects MAX.
- `/upgrade` is an optional legacy alias for STANDARD.
```

Restart Codex after installing the skill.
