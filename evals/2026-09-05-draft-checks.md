# 2026-09-05 draft: limited verification

**Draft with known bugs. Testing is ongoing.** This is not a completed benchmark or evidence of reliable Low/Medium/High performance.

## What changed

The draft adds two question-selection priorities within the existing limits:

- Ask about existing success requirements before proposing comparison or test criteria.
- Ask what is going wrong and what evidence shows it before offering optional methods for improving existing work.

It also publishes the previously prepared prompt-only, permission, missing-answer and final-comparison safeguards. The three modes and their question limits have not been redesigned.

## Question-selection spot checks

Two fresh Astra High conversations received only the candidate skill and one raw request each. Neither received the hidden intended result, a suspected bug, the proposed fix or earlier findings. The only follow-up before the question round was `Yes` to the intent echo. Session metadata confirmed `gpt-6-astra` with `high` effort.

| Request | Observed decision round |
|---|---|
| Compare two homemade bike-light brackets, not just appearance | Three questions. The first asked whether a definition of success, fixed limits or pass/fail checks already existed. |
| Improve a primary-school weather and climate activity that feels flat | Five questions. The first asked what felt flat, what showed it, and for an example or synthetic pupil feedback. It also asked about existing learning objectives and success checks. |

Both targeted question-selection checks were met. No hidden answers were supplied and neither conversation continued through final-prompt delivery. These checks therefore do **not** establish complete intent recovery, preservation of later answers, execution quality or an overall pass rate. They are not a controlled before/after comparison. The bracket question menu still favoured riding contexts, with other uses available through free text, so question framing remains worth testing.

## Other checks and remaining work

- The skill-creator frontmatter validator passed.
- Agent metadata and evaluation-case YAML parsed, with eight unique case IDs.
- Relative Markdown links resolved and Git whitespace checks passed.
- Earlier simulations exposed missed success criteria and uneven question selection. Independent auditing also found simulator contamination and excess clarification turns. Those conversations cannot be counted as a clean passing suite.
- The larger fixed-baseline comparison remains incomplete. This urgent tester draft is an explicit exception, not a mid-suite replacement of the original baseline.

The preserved baseline entrypoint has SHA-256 `555ddf31a99d3d9cae8ffc240ff87fa9048b97cb8f872fdf9586e8773f2e1856`. Its frozen case bank has SHA-256 `e114c0058ad6295ff3ba584164368d49d25795d40cb985743f679e018ca75b20`. Both remained unchanged during these checks.

For real-world testing, review the generated prompt before running it. Report missed requirements, added constraints, unnecessary questions and unclear stopping behaviour, with private information removed.
