# Astra Low, Medium and High: 27 October 2026

**All four targeted cases met the material checks at each setting. Keep this in proportion: one conversation per case and effort, on familiar regression cases, not a reliability benchmark.**

We ran 12 new conversations on the unchanged published skill and compared them with the four existing Ultra conversations from the [practical update](../2026-10-27-practical-update/README.md). Actual `gpt-6-astra` settings were verified from session records for every subject turn. No instruction or fixture changes, retries to replace poor results, or rescue answers were used during the batch.

## Results

| Actual clarification effort | Cases meeting material checks / valid cases | Valid / planned cases | User replies across four cases | Visible response words |
|---|---:|---:|---:|---:|
| Low | 4 / 4 | 4 / 4 | 9 | 1,437 |
| Medium | 4 / 4 | 4 / 4 | 9 | 1,492 |
| High | 4 / 4 | 4 / 4 | 9 | 1,578 |
| Ultra, previous comparator | 4 / 4 | 4 / 4 | 9 | 1,622 |

The checks covered preservation of material supplied requirements, no unsupported mandatory scope or permission expansion, correct readiness and confirmation stops, and prompt-only operation. These are **not** original-intent-match rates. The scripted replies intentionally supply a complete brief, including facts that may not have been individually elicited.

Visible word counts include all final-channel responses, including their labels and skill citations, but exclude commentary, tool output and hidden reasoning. They measure reading volume, not total tokens, cost, speed or human effort. The small differences should not be treated as a stable ranking.

### What held up at all four settings

- **MIN:** one confirmation, then a reusable proofreading prompt preserving Australian English, spelling/punctuation-only changes, wording, tone, facts, paragraph order and corrected-text-only output.
- **STANDARD investigation:** asked what the user observed, retained the query-reformulation and asking-colleagues symptom, and assigned the unknown diagnosis and realistic success checks to the later investigation. No invented agreed numeric target or system-change permission.
- **MAX:** kept the handover to one page, preserved the current rundown and supplied-source boundaries, retained explicit missing-information placeholders, and confirmed the end state before rendering. No new system or workflow was added.
- **Late permission decision:** asked draft-versus-send directly. After the user selected drafting, the final prompt prohibited sending or contacting anyone. This case needed three user replies at every setting.

## Review and decision

An independent reviewer assessed all 16 conversations in shuffled order with actual effort and source/version labels withheld. It found no material failures. The primary reviewer agrees. [Review findings and label mapping](review.json) are preserved, including minor concerns: repeated setup recommendations, procedural skill quotations, overlapping answer options in one Low MAX run, and less explicit final-message approval wording in an unused Ultra send option. None changed the selected draft-only permission boundary.

**Keep:** Low as a starting point for clarification tasks of this kind. In these examples, higher effort produced no material improvement identified by the reviewers, and Low used fewer visible words. This is a narrow working judgement, not a universal model recommendation.

**Test first:** broader claims about ambiguous, consequential or unusually complex briefs. Choose the eventual execution effort separately. A Low clarification run can still produce a prompt whose later research or implementation warrants Medium or High.

**No runtime changes:** this batch did not justify another rule or feature. The tested skill remains exactly the version shipped in commit `5d016c666ffeecd70597c825cf4ec107cd6d34e9`.

## Evidence and reproduction

- [Frozen plan](plan.json) and [runtime/fixture hashes](versions.json).
- Unchanged [three-mode fixtures](../2026-10-27-practical-update/cases.json) and [late-permission fixture](../2026-10-27-practical-update/followup-case.json).
- [Full user-facing transcripts](transcripts.json), with actual configuration for each turn. The four Ultra records are copied from the earlier report and clearly identified as previous comparators.
- [Per-run results, word counts and tool-call audit](results.json). Subject tools only read the isolated skill and linked references; no underlying task was executed.

Before publication, the recorded replies were checked against the fixtures, word and reply counts were recomputed, and runtime, fixture and plan hashes matched. The Ultra copies differ from the earlier records only in normalised snapshot paths. JSON, relative links, agent metadata, evaluation YAML and official skill validation passed.

For each case/effort, use a fresh subject with only the frozen runtime and raw request. Send the fixed replies at the corresponding stops, stopping at delivery or the fixture cap. Do not show subjects the rubric, answers or prior results, inject unused answers after delivery, or patch the skill during the batch. The [evaluation protocol](../PROTOCOL.md) explains the distinction between these workflow regressions and a frozen-intent study.

## Limits

There is only one observation for each of four cases at each setting. These cases were used during development, not held out. An AI reviewer and the primary agent agreeing is not independent human validation. The suite does not test recovery of a hidden intended result, downstream task execution, other models, real-world user satisfaction, external skill discovery, setup persistence, live integrations, high-stakes decisions or complex MAX work. The larger original-intent evaluation remains unfinished.

The next useful evidence would be unseen frozen-intent cases and real users' before/after task results, rather than repeatedly polishing these same examples. The project remains a draft with bugs; review generated prompts before running them.
