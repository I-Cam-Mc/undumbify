# Practical update: 27 October 2026

**Draft, limited evidence.** Four fixed scenarios were run on the published baseline, a first candidate and the corrected candidate: 12 fresh conversations in total. These are targeted workflow regressions, not evidence of hidden-intent recovery or better downstream task outcomes.

Session metadata confirmed **GPT-6 Astra, Ultra** for every subject turn. Recommendations of Low or Medium inside the generated replies describe the proposed later run, not the settings used in these tests. No Low/Medium/High reliability claim follows from this result.

## What changed in the observed runs

| Scenario | Published baseline | Final candidate |
|---|---|---|
| MIN, fully specified proofreading prompt | Delivered after one user reply; final response 164 words | Delivered after one user reply; final response 82 words; spelling/punctuation-only limits and future input preserved |
| STANDARD, investigate unhelpful search | Asked several questions and an extra success-check approval; decision-stage response 192 words | Asked one focused question about the observed problem; decision-stage response 61 words; final prompt preserved the reported symptom and left diagnosis to the investigation |
| MAX, practical radio-show handover | Repeated settled scope in a checklist and end-state paragraph; confirmation response 176 words | One end-state paragraph; confirmation response 106 words; delivered after confirmation with one-page, source and no-new-system constraints preserved |
| STANDARD, late draft-or-send decision | Asked permission to ask, then asked the permission choice; four user replies before delivery | Asked the actual choice directly; three user replies before delivery; final prompt explicitly prohibited sending or contacting anyone |

Word counts use whitespace-separated words in the recorded final-channel responses, including their visible labels and skill citations. They exclude tool output and commentary. These are single-run observations, not general performance estimates or measurements of model cost, reasoning tokens, elapsed time or human satisfaction.

The primary reviewer checked all four final prompts against the starting requests and supplied answers. Each delivered a usable prompt with the material supplied constraints preserved and no material unsupported additions identified. All remained prompt-only. Subject tool calls were inspected and consisted only of reads of the isolated skill and its references. No underlying task was executed.

## A regression caught before shipping

The first candidate delivered the STANDARD investigation prompt after the initial confirmation, without asking what “unhelpful” meant in practice. It did not receive the scripted symptom, audience or source-limit answer because it had already delivered. Its shorter conversation is **not** counted as a benefit or a complete intent match.

After completing all four first-candidate conversations, the rule was narrowed: vague quality judgements need a concrete observed problem or example before the brief is treated as complete. That is different from asking the user to diagnose the cause. If there are no observations, the prompt should explicitly scope exploratory work.

All four cases were then rerun with fresh subjects and unchanged requests and scripted replies. The corrected STANDARD run asked for the observed problem and preserved the answer in its final prompt. The other three retained their intended flows. This is a development regression check, not unseen generalisation evidence.

## Evidence and reproduction

- [Three mode fixtures](cases.json) and the [late-permission fixture](followup-case.json) were frozen before their baseline runs.
- [Full user-facing transcripts](transcripts.json) retain the baseline, rejected first candidate and final candidate. Temporary directory prefixes are replaced with `snapshot/`; no hidden reasoning or private user material is included.
- [Version hashes](versions.json) identify every runtime file and the frozen fixtures. Baseline: `cae6c37f3089c83cc71cc02cab2e3724b979d64a`.
- The `patch` field in the [first-candidate record](candidate-1-patch.json) reconstructs its runtime instructions from that baseline. The final candidate is the runtime shipped with this report.

For each case, start a fresh subject with only the selected runtime snapshot, its references and the raw request. Give the scripted replies in sequence at the corresponding stops. Stop at delivery or the stated cap; do not inject unused answers after delivery or add rescue turns. For the late-permission case, the frozen rule allows a single `Yes.` only if the subject asks permission for another round before asking the actual choice. Do not reveal expected outcomes, prior results or the proposed change to subjects.

The scripted decision replies intentionally provide a complete brief, including facts that may not have been individually elicited. They test handling and preservation, **not elicitation of a hidden intended result**. The original frozen-intent evaluation remains unfinished and is not replaced by this report.

## Other verification

- Official skill frontmatter validation passed.
- Agent metadata and eight unique evaluation definitions parsed successfully; explicit-only invocation policy was preserved.
- Relative Markdown links, runtime snapshot hashes and Git whitespace checks passed.
- An independent read-only consistency review found no release-blocking contradiction in routing, prompt-only operation, permission boundaries or MAX's final confirmation. It did not independently grade these transcripts.

## Still unproven

This small, hand-authored set does not establish general reliability, real-user effort savings, downstream task quality, or performance at other reasoning levels. External skill discovery, human-perspective research, setup persistence, user-declined follow-ups and live integrations were not exercised here. Some subjects still read optional references unnecessarily. Keep the draft warning, review generated prompts, and report real failures with private information removed.
