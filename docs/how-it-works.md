# How Undumbify works

Undumbify sits between a raw request and the run that does the work. Its job is not to make every prompt longer. It uses a small amount of clarification when that is cheaper than a wrong guess, wasted effort, weak evidence, extra scope or an impractical result.

All three commands follow the same basic pattern:

1. Say what the request appears to mean.
2. Resolve only choices that could change the result.
3. Make assumptions, limits and success checks visible.
4. Separate choices needed now from inputs and investigation work for the later run.
5. Describe the agreed end state.
6. Write the prompt, then compare it with every confirmed answer.

## `/undumb`: minimum useful confirmation

MIN is for requests that are almost ready. It has one required stop and should stay lighter than the request it improves.

| Stage | What it does | Why it exists |
|---|---|---|
| Combined readback | Says what the request appears to mean, asks up to two questions, and shows at most two assumptions | One short interruption can catch the largest meaning or scope error without turning a small task into a workshop |
| Question check | Skips questions whose answers would not change the work | On small prompts, too much ceremony can cost more than it saves |
| Question priority | Uses scarce questions for result-changing choices, not inputs that can safely remain run-time placeholders | A legal jurisdiction or comparison basis can matter more than asking for a file that will be attached later |
| Compact prompt | Returns the shortest self-contained prompt, normally with no more than five essential steps or bullets and no word-count floor | MIN should preserve momentum, not pad a clear request into a specification |
| Prompt as final check | Lets the prompt itself show the agreed destination | A separate summary would repeat the same information |
| Low-effort default | Usually recommends Low | Once the target is clear, many ordinary tasks need directness more than deeper exploration |

MIN succeeds when the user can answer quickly, recognise their intent in the prompt and run it without discovering surprise scope.

## `/undumbify`: standard confirmation

STANDARD is the default for serious work. It separates the meaning check from the decision questions. This stops detailed questions from being built around a wrong first interpretation.

| Stage | What it does | Why it exists |
|---|---|---|
| Stop 1, intent echo | Reads back the intended outcome, use and main uncertainty | The user can correct double meanings, audience or purpose before the model gathers context or designs a method |
| Smallest useful context | Reads only previous decisions, supplied material or current facts that could change the prompt | Useful context improves continuity. Broad context adds delay, stale assumptions and distraction |
| Stop 2, decision round when needed | Asks up to five independent decisions with the largest likely effect, including assumption and success-check approvals | Counting actual decisions prevents extra questions from hiding under one label. A complete brief skips this round |
| Easy answers | Uses short lettered choices, up to A-D, or free text where clearer | Compact answers reduce effort; four options are not a quota |
| Neutral preferences | Avoids recommending answers to matters of taste | A recommendation can anchor the user and make the test measure agreement instead of understanding |
| Assumptions and success | Separates confirmed needs, assumptions and optional ideas, then chooses visible success checks | Plausible guesses should not quietly become requirements |
| Evidence and complexity limits | Says how much checking and process are enough | More sources and more components have costs, so they need a reason |
| Missing-information check | Separates user choices from facts to investigate and inputs to supply later | A permission decision must not be guessed, but an investigation prompt does not need its findings in advance |
| End-state checksum | Summarises the finished artefact, boundaries, evidence and success just before the prompt | The user can compare the compiled prompt with the intended destination without replaying the discussion |
| Final comparison | Checks the prompt against the original request and every confirmed answer | This catches drift introduced while turning the discussion into a polished prompt |
| Model recommendation | Chooses the suitable model and lowest sufficient effort for the later run | Clarification depth and execution difficulty are different things |

STANDARD normally writes the prompt after the second answer. If that answer exposes a consequential user choice, it explains why it matters and asks the question directly. There is no extra exchange asking permission to ask. One short follow-up is allowed beyond the normal flow; if the choice remains unresolved, the skill stops and names it unless the user requests more clarification.

## `/undumbifyMAX`: deeper alignment

MAX is for work where a wrong interpretation, weak evidence rule or unrealistic method would be costly. It adds a third checkpoint, not unlimited questioning.

| Stage | What it does | Why it exists |
|---|---|---|
| Stop 1, intent echo | Confirms the central meaning without starting with a checklist | Even high-impact work should begin with the cheapest test of shared understanding |
| Context and decisions | Inspects relevant sources and asks up to five high-value questions | MAX earns its extra depth through better choices and evidence, not a longer generic questionnaire |
| Stop 2, decision round | Confirms output, evidence, tools, perspectives, success and known risks only when relevant | Optional modules stay optional and the user chooses which kinds of rigour are worth paying for |
| Internal alignment check | Checks requirements, assumptions, optional ideas, evidence, non-goals, permissions and when to stop without printing another specification | The model should do the consistency work rather than make the user re-read every settled answer |
| Missing-information check | Resolves material user choices and explicitly assigns future inputs and investigation work | MAX should not hide a decision inside an assumption or demand the answer to a research task in advance |
| Reality and simplicity checks | Tests ordinary practice, likely human behaviour and whether every component prevents a named failure | A model can produce a logically neat system that nobody would use |
| Stop 3, end-state checksum | Describes the completed state in one short paragraph and asks for confirmation | This comes last because it must reflect the decisions already made. It replaces a duplicated requirements packet, not the confirmation gate |
| Final comparison | Checks the finished prompt against the request and every confirmed answer | Extra detail creates more chances for silent scope growth, so MAX needs a strong last check |
| Medium-effort default | Usually recommends Medium, with High only for genuinely difficult execution | MAX means deeper clarification. It does not prove the later task needs extreme reasoning |

## What the final comparison prevents

Question selection comes first: for comparisons and tests, establish any existing success requirements before proposing criteria. For improvements to existing work, find out what is going wrong and what examples show it before offering optional methods. These priorities use the existing question budget; they do not create another stage or force questions when the answers are already clear.

The final comparison is deliberately strict:

- every important confirmed point must still be present;
- an explicit constraint cannot be weakened;
- a list of allowed actions is complete, so nearby actions remain prohibited;
- a new exact count, threshold, time limit, required tool, exclusion, method or chosen option cannot appear unless the user confirmed it or it is strictly needed by something they confirmed; and
- a useful unconfirmed idea must stay clearly optional.

This is different from checking whether the prompt sounds good. It checks whether the prompt still means what the user confirmed.

## Optional modules

Optional modules are used only when a named failure makes them useful:

- **External skill discovery** fills an important capability gap. It can search beyond installed skills, but checks the actual instructions, trust, maintenance, testing, popularity and independent acclaim.
- **Human reality check** helps when lived experience, adoption, culture or ordinary practice could invalidate a purely logical answer.
- **Unlazy handoff** helps when the later task has several separate obligations and partial completion could look like success.
- **First-use setup** saves preferences only after the first useful prompt and only with permission. Installation itself cannot run an interview.

A safeguard used on every prompt becomes ceremony. A safeguard used for a named risk stays useful.

## What can wait until the later run?

- **“I will attach the newsletter then.”** Keep an explicit input placeholder. Do not demand it now just to prepare a proofreading prompt.
- **“Find out why search is unhelpful.”** Ask what the user observes or for an example, then define the investigation. Do not ask for the diagnosis. If there are no observations yet, make that exploratory starting point explicit.
- **“I have not decided whether you may email customers.”** Ask the actual permission question. Do not assume consent or hide the choice in the prompt.

If the user declines a necessary decision, label any useful partial prompt as incomplete and name what must be settled before running it. The ability to skip questions is not permission to guess consequential answers.

## Why another round always means more questions

The final `Another clarification round?` option does not permit a silent rewrite. A new round must identify a new important gap and ask the best available question. If no such question remains, the prompt stays unchanged.

## What success looks like

Undumbify has succeeded when:

- the user recognises their intended meaning in the readback;
- every question could plausibly change the result;
- assumptions are visible and important choices are confirmed;
- no unresolved user decision is silently chosen, and future inputs or investigations are explicit;
- the final prompt preserves every confirmed instruction and permission boundary;
- evidence and complexity match the cost of being wrong;
- the recommended effort is based on the later task, not the clarification mode; and
- the underlying task has not been run.
