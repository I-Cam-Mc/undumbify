# Changelog

Material upgrades to Undumbify are recorded here so users can see what changed, why it changed, and which behaviour deserves renewed testing.

## 2026-09-05: draft for testing

**Testing is ongoing. This draft has known bugs and is not a validated reliability release.** Review generated prompts before execution. The larger fixed-baseline comparison remains incomplete; no overall success rate or lower-effort performance claim is made.

### Upgraded

- Prioritises the user's existing success requirements, fixed limits and pass/fail checks before inventing evaluation criteria.
- Prioritises the actual problem and supporting examples when improving existing work, before optional methods or modules. Neither change adds a stage or raises the question limit.
- Added a prominent draft warning, a frozen-intent evaluation protocol and guidance for reporting bugs without exposing private information.
- Slimmed the always-loaded skill entrypoint and moved STANDARD, model routing, human-reality checks and Unlazy handling into conditional references.
- Clarified that published stop counts describe required confirmations before prompt delivery; an optional additional clarification round is separate.
- Distinguished confirmed assumptions, safe open points, and missing answers that block confirmation.
- Made skill discovery unambiguously prompt-only: candidates cannot be installed, executed or granted permissions during Undumbify.
- Added a freshness rule for model catalogues and clarified that recommendations apply to the later execution run.
- Delayed the setup questionnaire until a useful first prompt has been delivered and the user chooses setup.
- Reworked the GitHub landing page around the problem Undumbify solves, mode selection, Astra-oriented design and a visual before/after flow.
- Added a stage-by-stage explanation for MIN, STANDARD and MAX.
- Added behavioural evaluation cases and invited real-world testing, failure reports and suggestions.
- Added a missing-answer check: the prompt is not ready while an unanswered point could change the result, scope, permissions, cost or meaning of success.
- Added a final comparison against the original request and every confirmed answer so the rendering step cannot silently weaken constraints or add hard requirements.
- Treats a user's list of allowed actions as complete. Nearby actions stay prohibited unless approved.
- Made A-D choices the default for STANDARD and MAX decision questions, while keeping preference questions neutral and limiting recommendations that could anchor the user's answers.
- Improved MIN question priority so run-time placeholders do not crowd out governing jurisdiction, protected material, permissions or the basis of comparison.

### Verification limits

Two fresh Astra High conversations met the targeted question-selection checks. They stopped before final-prompt delivery, so they do not establish complete intent recovery or a completed regression suite. Structural checks passed. See [draft checks](evals/2026-09-05-draft-checks.md) for the scope, remaining risks and preserved baseline.

### Please re-test

- Whether existing acceptance criteria are elicited and preserved instead of replaced with model-proposed thresholds or durations.
- Whether refinement of existing work asks for the observed problem and evidence before offering optional process additions.
- Whether `/undumb` stays materially lighter than the other modes.
- Whether STANDARD asks only questions that could change the result.
- Whether MAX catches unrealistic or overengineered approaches without suppressing deliberate creativity.
- Whether model and effort recommendations remain proportionate to the eventual task.
- Whether the final prompt matches a user's pre-existing intent even when the raw request starts vague.
- Whether new numbers, tools, exclusions or methods remain optional until confirmed.
