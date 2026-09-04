# Frozen-intent evaluation

Test the skill, not the simulated user's ability to repair its output. The original intended result is fixed before the conversation begins. A user changing the brief is not a success criterion.

## Roles and sequence

1. An independent case author freezes a raw request, atomic intended requirements, exact allowed answers and any genuinely undecided choices. Record a SHA-256 hash before testing. Run the complete planned baseline set before selecting a batch of skill changes. Reserve separate unseen cases only when testing generalisation.
2. A fresh subject receives only the raw request and a versioned skill snapshot, not the answers, rubric, earlier results or proposed fix. Read-only synthetic fixtures avoid live account actions. Record the actual model and effort when available; never infer them from a recommendation in its reply.
3. A restricted simulator answers only questions actually asked. Each reply has a receipt linking a quoted question to frozen fact IDs and explaining how that question explicitly invites each fact. Corrections quote the contradictory echo. Provenance alone does not prove elicitation. Copy the corresponding answer sentences exactly. For an unrecorded preference, answer `Not specified`, not a newly invented preference.
4. Preserve all subject messages, simulator receipts and final prompts. Do not patch the skill during a suite. Independently audit both the answers and the final prompts after the conversations.
5. Review the combined baseline results and make one batch of justified changes. Freeze the candidate, then rerun the same cases with unchanged intended results, simulator rules, model and effort. Report improvements, regressions and unchanged failures. These paired reruns are not new independent successes. Use separate unseen cases for generalisation, not as a substitute for a before/after comparison.

If an explicitly authorised urgent draft is published before that comparison finishes, preserve the original baseline and label the publication as an exception. Do not relabel its spot checks as the completed evaluation. The 2026-09-05 draft is such an exception.

## Simulator boundaries

- A specific question about constraints, evidence or success can elicit several relevant facts. A broad question is not automatically a bad question.
- An intent echo may be corrected when it contradicts a fact. Merely omitting a hidden requirement does not permit the simulator to volunteer it at confirmation.
- `Is that right?` and `Anything else?` do not authorise dumping the entire hidden brief.
- Never accept an unsupported addition just to progress. Say it is not specified. Do not convert that into a new prohibition either.
- Allow at most one requested extra decision round when the named choice has an answer in the frozen brief. Decline when it is genuinely undecided or no specific choice is named. Do not answer post-delivery offers. Never add a rescue turn because a score looks poor.
- If a reply leaks an unasked fact, invents an answer or changes the intended result, invalidate the affected case as evidence of recovery. Keep the transcript and describe the protocol failure.

## Report separate outcomes

| Measure | What it establishes |
|---|---|
| Elicitation | Which original material requirements were actually requested and supplied, before the final prompt |
| Preservation | Which supplied requirements survive in the final prompt with the same strength and scope |
| Original-intent match | Whether the final prompt covers the complete frozen target, including requirements the subject failed to elicit |
| Unsupported additions | New mandatory scope, constraints, methods, numbers, permissions or preferences, including treating a preference as a requirement |
| Readiness | Whether the subject correctly delivers a usable prompt or names a genuinely unresolved decision without claiming readiness |
| Interaction burden | Substantive questions, user turns, clarification stops and response length; count multipart decision demands, not only numbered labels |
| Protocol integrity | Whether isolation, frozen versions, exact answers and the no-rescue rule were maintained |

Report missed requirements even when the subject reasonably says it cannot finish. A correct pending result is distinct from a ready prompt that matches intent. Harmless placeholders are distinct from unanswered decisions that change the result.

Freeze material requirements with the bank. A complete intent match requires all of them, unchanged strength and scope, exact permission boundaries, no material unsupported additions, correct readiness and valid protocol. Coverage alone is insufficient.

Do not use simulator satisfaction, number of corrections, a polished-looking prompt or workflow compliance as a substitute for intent match. Report first-attempt failures, not just the latest passing version. Show both `matched / valid cases` and `valid / all frozen cases` together. Invalid cases stay visible; never describe the entire suite as passing when any case is invalid.

These simulations test prompt elicitation and compilation. They do not prove that executing the prompt improves real task outcomes, or that a skill tested at one reasoning effort works equally well at another. A before/after claim needs comparable cases and a controlled comparison, not just different development and holdout scores.
