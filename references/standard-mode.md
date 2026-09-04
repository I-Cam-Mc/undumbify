# STANDARD mode

Use STANDARD for serious requests where the main idea is visible but the scope, evidence, limits, output or success may still need confirmation.

## Stop 1: Intent echo

Give the core one-paragraph readback and wait. This catches meaning errors before context gathering or detailed questions are built around the wrong interpretation.

## Context and decisions

After confirmation:

1. Retrieve only context likely to change the prompt.
2. Resolve discoverable facts through read-only work when that is easier than asking the user.
3. Ask no more than five highest-value questions in one compact round.
4. Present no more than three important assumptions that still need confirmation.
5. Offer only success checks whose selection would affect execution or verification.

External discovery is optional, not a routine step. Use it only when a current fact or named capability gap could change the prompt in an important way.

## Stop 2: Decision round

Combine the questions, assumptions and proposed success checks. Default each decision question to A-D choices, with D as `Other / specify` when useful. Use Yes/No for binary choices. Ask openly only when fixed choices would hide information needed for a safe or correct result. Allow compact answers such as `1B, 2D: ...`.

Do not recommend a full answer bundle. Keep preference questions neutral. Recommend one option only when known facts make it clearly safer or more effective, and put that recommendation below the choices.

After the answers, apply the core missing-answer check. Render without a routine third stop only when no missing answer could change the result. Otherwise, name the missing choice and ask whether the user wants one more clarification round. Ask the new question only after a yes.

## Render

Write the target-state checksum immediately above the copy-ready prompt. Include confirmed requirements and assumptions, but do not copy the clarification conversation into the prompt.

Before delivery, run the core final comparison. The prompt must preserve every confirmed answer, keep the user's permission list closed, and avoid new hard numbers, tools, exclusions or methods that the user did not choose.

STANDARD should normally recommend Low effort. Use Medium only when the eventual task still needs difficult research, several interacting constraints, or substantial verification after clarification.
