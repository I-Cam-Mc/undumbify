# First-use setup

Read this file only when the user selects setup or explicitly invokes `$undumbify setup`. If no preferences were available during the preceding round, that round should already have proceeded with the defaults below rather than delaying the request.

Setup is optional and happens after a usable prompt. Append it to the ordinary next-round choice rather than creating another required confirmation stop:

`Another clarification round? Yes / No. On first use, add "+ setup" to configure future defaults.`

If the user adds `setup` or explicitly invokes `$undumbify setup`, ask one compact setup questionnaire. Do not imply that installation itself can ask questions.

Gather no more than five setup decisions:

1. The ChatGPT, Codex, or other surface where prompts normally run, including the currently available model and effort catalogue when known.
2. The optimisation priority. Default recommendation: best reliable result at the lowest sufficient effort. Alternatives may prioritise maximum quality, speed, or cost.
3. Context behaviour: automatically retrieve the smallest relevant read-only memory, show context hooks first, or avoid memory retrieval.
4. External skill discovery: bounded search when an important capability is missing, MAX only, or never.
5. Optional escalation preferences: when relevant, whether to ask about human perspectives and whether to ask before suggesting Unlazy.

Use concise A-D choices where practical and allow free text for catalogues or invocation syntax. Ask permission before saving. Saving consent is not one of the five setup decisions. Save only confirmed preferences through the available durable memory system and verify the saved result when possible.

If durable memory is unavailable, say the preferences can only be reused in the current conversation. Run setup again only when the user asks, a saved option is no longer available, or the model list may be out of date.

Defaults when the user declines setup or storage:

- best reliable result at the lowest sufficient effort;
- smallest relevant read-only context retrieval;
- bounded external skill discovery only when an important capability is missing;
- ask before adding a human-perspective module;
- ask before suggesting Unlazy, and only when its full gate is satisfied.
