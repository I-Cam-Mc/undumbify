# MAX mode

Use MAX for high-impact, very unclear, research-heavy, multi-domain, or unusually creative work where the user wants deeper clarification. MAX adds scoping depth, not reasoning effort by default.

## Stop 1: Intent echo

Use the same short paragraph as other modes. Do not front-load a checklist just because MAX was invoked. Wait for confirmation.

## Context and decision work

After confirmation:

1. Retrieve the smallest relevant memory and inspect supplied materials.
2. Identify current facts requiring verification, previous decisions, potentially ambiguous terminology, relevant examples, and missing source material.
3. Ask no more than five highest-value questions in one decision round.
4. Apply the core missing-information rule. Distinguish user choices from findings to investigate and inputs to supply later. If a consequential choice emerges after the round, ask it directly in one short follow-up before the end-state check. Do not silently choose or insert a permission-to-ask exchange.

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

Present no more than five independent decisions in one compact round, including any assumption or success-check approvals. Prefer useful lettered choices, up to A-D, with free text always allowed. Skip the decision round if no consequential gap remains. Do not invent questions or options to justify MAX.

Do not recommend a full answer bundle. Keep preference questions neutral. Recommend one option only when known facts make it clearly safer or more effective, and put that recommendation below the choices.

## Check alignment without a packet

After the answers, check the following internally where relevant, not as a mandatory user-facing list:

- confirmed outcome and audience;
- user-stated requirements;
- confirmed Assumptions A-D and explicit inputs or findings for the later run;
- selected and rejected suggestions;
- evidence and source standard;
- human-reality-check requirement, if selected;
- success checks;
- explicit non-goals and the complete list of actions the executor may take;
- complexity budget and stopping condition;
- capability gaps, proposed tools, and skill-search result when relevant;
- the recommended reasoning effort and why.

Do not let optional modules become requirements without confirmation. Do not print an empty assumptions list, a list of absent modules or a second summary of the user's answers.

If a consequential user decision is unresolved, ask about it before the final check. Never present a guessed choice as confirmed. Unfinished investigation work can remain in a ready prompt.

## Stop 3: Target-state checksum

Show one short paragraph written from the perspective of the desired completed state:

`At the end, the executor will have ...`

The paragraph should make the intended artefact, use, boundaries, evidence, and success conditions easy to verify. Add a short exception note only if a material assumption or unresolved input would otherwise be hidden. Ask for yes or a correction. Render only after confirmation. If the user corrects it, update the affected point and seek confirmation of the changed end state without restarting settled questions. Do not reprint the confirmed summary when delivering the self-contained prompt.

Before delivery, compare the final prompt with the confirmed request and every answer. Preserve every important point. Keep the user's allowed-action list closed. Remove any new hard number, tool, exclusion, method or selected option that the user did not confirm and that is not strictly required by a confirmed need.

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
