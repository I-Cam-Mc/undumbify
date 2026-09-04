# MAX mode

Use MAX for high-impact, very unclear, research-heavy, multi-domain, or unusually creative work where the user wants deeper clarification. MAX adds scoping depth, not reasoning effort by default.

## Stop 1: Intent echo

Use the same short paragraph as other modes. Do not front-load a checklist just because MAX was invoked. Wait for confirmation.

## Context and decision work

After confirmation:

1. Retrieve the smallest relevant memory and inspect supplied materials.
2. Identify current facts requiring verification, previous decisions, potentially ambiguous terminology, relevant examples, and missing source material.
3. Ask no more than five highest-value questions in one decision round.
4. Record only unanswered points that cannot change the result in an important way. If a missing answer could change the result, resolve it before the target-state checksum. Do not silently exceed the stop limit. Name what is missing, ask whether the user wants an extra clarification round, and ask the new question only after a yes.

Offer relevant choices rather than automatically adding:

- response or artefact shape;
- evidence depth and source hierarchy;
- inspiration, examples, or reference materials;
- tools and other resources;
- human or practitioner perspectives;
- external skill discovery;
- acceptance criteria or meaningful KPIs;
- known failure modes and adversarial checks.

## Stop 2: Decisions

Present the questions in one compact round. Default each decision question to A-D choices, with D as `Other / specify` when useful. Use Yes/No for binary choices. Ask openly only when fixed choices would hide information needed for a safe or correct result. Allow compact replies such as `1B, 2D: ...`.

Do not recommend a full answer bundle. Keep preference questions neutral. Recommend one option only when known facts make it clearly safer or more effective, and put that recommendation below the choices.

## Alignment packet

After the answers, prepare a concise packet containing:

- confirmed outcome and audience;
- user-stated requirements;
- confirmed Assumptions A-D and any unanswered points that are safe to leave open;
- selected and rejected suggestions;
- evidence and source standard;
- human-reality-check requirement, if selected;
- success checks;
- explicit non-goals and the complete list of actions the executor may take;
- complexity budget and stopping condition;
- capability gaps, proposed tools, and skill-search result when relevant;
- the recommended reasoning effort and why.

Do not let optional modules become requirements without confirmation. Add `Missing answers that could change the result: none` only after applying the core missing-answer check.

If a missing answer could still change the result, it is a blocker rather than an assumption. Do not present the packet or later prompt as confirmed.

## Stop 3: Target-state checksum

End the alignment packet with one paragraph written from the perspective of the desired completed state:

`At the end, the executor will have ...`

The paragraph should make the intended artefact, use, boundaries, evidence, and success conditions easy to verify. Ask for yes or a correction. Render the final prompt only after confirmation. In the final response, do not reprint the confirmed checksum, alignment packet, or assumptions when the self-contained prompt already carries them.

Before delivery, compare the final prompt with the confirmed request, every answer, and the alignment packet. Preserve every important point. Keep the user's allowed-action list closed. Remove any new hard number, tool, exclusion, method or selected option that the user did not confirm and that is not strictly required by a confirmed need.

## Reality and anti-overengineering checks

Before rendering, check:

- What evidence would change the conclusion?
- Does the approach conflict with relevant base rates or ordinary practice?
- Does it depend on idealised behaviour that should be explicit?
- Would a competent practitioner recognise it as workable in real life?
- Is an unconventional choice deliberate and justified rather than accidental?
- Does every added component prevent a named failure or satisfy a confirmed requirement?
- Could a shorter prompt preserve the same decision-relevant information?

Use external human opinions only when they add relevant practice or lived-experience evidence. Include both corroborating and dissenting perspectives where useful, without equating popularity with truth.
