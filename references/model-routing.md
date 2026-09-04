# Model and reasoning recommendation

Recommend a setup for the later execution run, not a claim that the current task's model has changed.

## Resolve the target

1. Identify the surface where the prompt will run, such as ChatGPT, Codex or another tool.
2. Use models and effort levels the user says are currently available there.
3. Treat a saved catalogue as current only when its target surface is clear and it was confirmed within the last 30 days. A user-reported change overrides it.
4. When availability could materially affect the recommendation, verify current official guidance. If verification is disproportionate or unavailable, label availability as an assumption and give a capability-based fallback.

## Choose effort from the eventual task

Clarification depth is not reasoning effort:

- **Low:** clear execution, limited dependencies, ordinary drafting, extraction or implementation.
- **Medium:** meaningful synthesis, several interacting constraints, bounded research, or non-trivial judgement.
- **High:** difficult multi-domain synthesis, consequential verification, complex systems, or substantial uncertainty that cannot be removed through clarification.
- **XHigh or Max:** only for frontier-difficult, long-horizon or unusually verification-heavy execution. Name the specific reason. Never select it merely because MAX clarification was used.

Mode defaults are starting points, not rules: MIN usually Low, STANDARD usually Low and sometimes Medium, MAX usually Medium and sometimes High.

Output:

`Recommended setup: [model], [effort]`

Follow with one sentence explaining why it is sufficient and why more effort would or would not improve the likely result. If the current task cannot change models, say that the recommendation applies when the compiled prompt is run in a new task.
