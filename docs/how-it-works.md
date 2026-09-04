# How Undumbify works

Undumbify is a confirmation layer between a raw request and execution. Its purpose is not to make every prompt longer. It spends a small amount of clarification where that is cheaper than inconsistent assumptions, misplaced effort, inadequate evidence, excessive scope or an impractical result.

All three commands use the same reasoning pattern at different depths:

1. Confirm what the request means.
2. Resolve only decisions that could materially change the result.
3. Expose assumptions and define sufficient evidence and complexity.
4. Describe the agreed end state.
5. Compile a prompt for a separate execution run.

## `/undumb`: minimum useful confirmation

MIN is for requests that are almost ready. It provides one required confirmation stop and should usually remain shorter than the request it improves.

| Stage | Behaviour | Why it exists |
|---|---|---|
| Combined readback | Echo the intended meaning, ask up to two questions, and show at most two assumptions | One compact interruption catches the largest semantic or scope error without turning a simple request into a workshop |
| Materiality test | Skip questions whose answers would not change execution | Small prompts are most vulnerable to ceremony costing more than the expected improvement |
| Compact render | Return a 150 to 300 word prompt with no more than five essential steps or bullets | MIN should preserve the user's momentum and prevent the model from inventing a process architecture |
| Prompt as checksum | Let the final prompt itself express the agreed end state | A separate summary would duplicate information and create a second ritual |
| Low-effort default | Usually recommend Low reasoning | Once the target is clear, many ordinary tasks benefit more from directness than deeper search through possibilities |

MIN is successful when the user can answer quickly, recognise their intent in the result, and run the prompt without discovering new scope.

## `/undumbify`: ordinary request compilation

STANDARD is the default for substantive work. It separates interpretation from decision-making so the detailed questions are not derived from an unconfirmed premise.

| Stage | Behaviour | Why it exists |
|---|---|---|
| Stop 1, intent echo | Read back the intended outcome, use and main uncertainty | Users can correct word meanings, implied audiences or mistaken goals before the model retrieves context or designs a method |
| Smallest relevant context | Retrieve only prior decisions, supplied materials or current facts that could alter the prompt | Context improves continuity, but broad retrieval adds latency, stale assumptions and distraction |
| Stop 2, decision round | Ask up to five questions ranked by expected impact | Forcing five questions creates filler. Capping the round prevents interrogation and makes answers easy to provide together |
| Assumption and success alignment | Separate confirmed requirements, assumptions and suggestions; choose observable success checks | Models commonly turn plausible inferences into requirements or optimise for generic quality rather than the user's actual definition of success |
| Evidence and complexity budget | State how wrong the result can afford to be and what level of research or process is sufficient | More evidence and more components have costs. The budget protects against both under-checking and reflexive overengineering |
| Target-state checksum | Summarise the final artefact, boundaries, evidence and success immediately before the prompt | This lets the user compare the compiled prompt with the intended destination without replaying the whole clarification process |
| Model recommendation | Choose the suitable available model and lowest sufficient effort for the later run | Clarification depth and execution difficulty are different variables. A carefully scoped prompt may need less reasoning, not more |

STANDARD normally renders after the second answer. If the answer reveals a new consequential decision, it should say that the prompt is not yet confirmed and offer another round rather than hiding the uncertainty.

## `/undumbifyMAX`: consequential alignment

MAX is for work where a wrong interpretation, weak evidence standard or unrealistic method would be costly. It adds a third required checkpoint, not unlimited questioning.

| Stage | Behaviour | Why it exists |
|---|---|---|
| Stop 1, intent echo | Confirm the central interpretation without front-loading a checklist | Even high-stakes work should begin with the cheapest possible test of whether model and user mean the same thing |
| Context and decision work | Inspect relevant sources and ask up to five highest-value decisions | MAX earns its extra depth through better-selected evidence and decisions, not a longer generic questionnaire |
| Stop 2, decision round | Confirm output shape, evidence, tools, perspectives, criteria and known risks only where relevant | Optional modules stay optional. The user controls which kinds of rigour the eventual task actually needs |
| Alignment packet | Show confirmed requirements, assumptions, rejected suggestions, evidence standard, non-goals, capability gaps and stopping condition | Consequential prompts need provenance. The packet makes scope expansion and hidden assumptions visible before they are compiled |
| Reality and anti-overengineering checks | Test base rates, operational plausibility, idealised behaviour and whether every component prevents a named failure | Powerful models can produce internally coherent but impractical systems. This check challenges that failure without forcing conventionality |
| Stop 3, target-state checksum | Describe the completed state and obtain explicit confirmation | The checksum comes last because it must reflect the earlier decisions. Using it first would merely encode the model's initial guess |
| Final render | Compile only the confirmed material and omit the deliberation transcript | The executor needs a precise brief, not the history of how the brief was negotiated |
| Medium-effort default | Usually recommend Medium, with High only for genuinely difficult execution | MAX signifies higher clarification investment. It does not prove the later task needs extreme reasoning |

## Optional modules

Optional modules are loaded only when a named failure makes them useful:

- **External skill discovery** addresses a material capability gap. It widens beyond installed skills but evaluates actual instructions, trust, maintenance, testability, popularity and independent acclaim.
- **Human reality check** addresses tasks where lived experience, adoption, culture or operational practice could invalidate a purely logical answer.
- **Unlazy handoff** addresses execution tasks where several obligations must all be verified and partial completion could look successful.
- **First-use setup** stores preferences only after the first useful prompt and only with permission. Installation itself cannot conduct an interview.

This conditional loading is part of the design. A safeguard that appears in every prompt becomes ceremony; a safeguard loaded in response to a named risk remains useful.

## Why another round always requires questions

The final “Another clarification round?” option does not authorise silent rewriting. A new round must identify new material uncertainty and ask the best available questions. If no such questions remain, the current prompt stays unchanged.

## What success looks like

Undumbify has succeeded when:

- the user recognises their intended meaning in the readback;
- every question could plausibly change the output;
- assumptions are visible and consequential decisions are confirmed;
- evidence and complexity match the cost of being wrong;
- the final prompt is shorter than the process it prevents;
- the recommended effort is justified by the eventual task, not by the chosen clarification mode;
- the underlying task has not been executed.
