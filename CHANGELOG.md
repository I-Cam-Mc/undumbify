# Changelog

Material upgrades to Undumbify are recorded here so users can see what changed, why it changed, and which behaviour deserves renewed testing.

## Unreleased

### Upgraded

- Slimmed the always-loaded skill entrypoint and moved STANDARD, model routing, human-reality checks and Unlazy handling into conditional references.
- Clarified that published stop counts describe required confirmations before prompt delivery; an optional additional clarification round is separate.
- Distinguished confirmed assumptions, non-blocking residual uncertainty and consequential unresolved decisions.
- Made skill discovery unambiguously prompt-only: candidates cannot be installed, executed or granted permissions during Undumbify.
- Added a freshness rule for model catalogues and clarified that recommendations apply to the later execution run.
- Delayed the setup questionnaire until a useful first prompt has been delivered and the user chooses setup.
- Reworked the GitHub landing page around the problem Undumbify solves, mode selection, Astra-oriented design and a visual before/after flow.
- Added a stage-by-stage explanation for MIN, STANDARD and MAX.
- Added behavioural evaluation cases and invited real-world testing, failure reports and suggestions.

### Please re-test

- Whether `/undumb` stays materially lighter than the other modes.
- Whether STANDARD asks only questions that could change the result.
- Whether MAX catches unrealistic or overengineered approaches without suppressing deliberate creativity.
- Whether model and effort recommendations remain proportionate to the eventual task.
