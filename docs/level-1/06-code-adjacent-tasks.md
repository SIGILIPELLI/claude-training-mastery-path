# 06 · Using Claude for Code-Adjacent Tasks

You don't need to be a programmer to get value from Claude on code-related
work — explaining what a piece of code does, reviewing it for obvious
issues, and generating a first-draft script are all approachable even if
you're not going to write the code yourself. This module covers those three
uses at a general level, without assuming any specific programming
background or tool integration (those specifics change often — check
current documentation for anything tool-specific).

## Explaining code

If you're handed a script, formula, or snippet you didn't write and don't
fully follow, Claude is generally good at translating it into plain
language.

| Weak prompt | Stronger prompt |
|---|---|
| "What does this do?" | "Explain what this code does, in plain English, assuming I understand basic programming concepts (variables, loops) but not this specific language." |
| "Explain this." | "Explain this spreadsheet formula step by step — what each part does and what the final result represents." |

**Worked example:**

> You're handed a script by a colleague and asked to sanity-check it before
> it runs on real data. Prompt: "Explain what this script does, section by
> section. Flag anything that looks like it modifies or deletes data,
> specifically."
>
> This framing does two things: it gets you an explanation you can actually
> follow, and it directs attention to the part that matters most for your
> purpose (not breaking anything), rather than a generic walkthrough.

## Reviewing for obvious issues

Even without deep programming knowledge, asking Claude to review code for
specific categories of problem — not just "is this good" — gives you
something concrete to act on.

| Vague review prompt | Specific review prompt |
|---|---|
| "Is this code good?" | "Review this for anything that looks like it could fail silently or produce wrong results without an obvious error — I need to trust this before it runs on real customer data." |
| "Check this." | "Check this for anything a beginner commonly gets wrong, like unhandled edge cases or hardcoded values that should be configurable." |

A useful habit for non-programmers: ask Claude to explain *why* something
flagged is a problem, in plain language, so you can judge whether it matters
for your situation rather than accepting or rejecting the flag blindly.

## Generating a first-draft script

Claude can generate a first draft of a small script or formula from a plain
description of what you want it to do — treat this the same way you'd treat
a first draft of writing: a starting point to review, not something to run
unverified on anything that matters.

| Weak generation prompt | Stronger generation prompt |
|---|---|
| "Write me a script to organize my files." | "Write a script that goes through a folder and moves any file older than 90 days into a subfolder called 'archive'. Explain what it does before I run it, and tell me how to undo it if something goes wrong." |
| "Give me a formula for this." | "Give me a spreadsheet formula that flags any row where the 'amount' column exceeds $500 and the 'approved' column is blank. Explain each part of the formula." |

Notice the pattern in the stronger prompts: describe the goal precisely,
and explicitly ask for an explanation and a safety note (how to verify
or undo) before treating the output as safe to run.

## A general safety habit

For anything Claude generates that will actually execute or modify data:

| Habit | Why |
|---|---|
| Ask for an explanation alongside the code | So you understand what you're about to run, not just trust it blindly |
| Test on a small or non-critical sample first | Limits the damage if something behaves unexpectedly |
| Ask "what could go wrong with this?" explicitly | Surfaces edge cases Claude may not have flagged unprompted |
| Keep a way to undo or roll back | Especially for anything that deletes or overwrites data |

## Cheat sheet: code-adjacent prompts

| Goal | Prompt pattern |
|---|---|
| Understand unfamiliar code | "Explain step by step, assuming [your actual background]" |
| Review for issues | Name the specific category of concern (silent failures, edge cases, hardcoded values) |
| Generate a script/formula | Describe the goal precisely, ask for an explanation and any risks alongside it |
| Before running anything real | Ask "what could go wrong," test small first, keep an undo path |

## How It Actually Works

Code looks very different from prose, but Claude processes it through the
same tokenization-and-attention pipeline described in Module 1 — with a few
code-specific wrinkles worth knowing.

**Code is tokenized differently than you'd expect.** Common keywords,
operators, indentation patterns, and frequent variable-naming conventions
each get their own tokens or short token sequences, learned from the huge
amount of code in training data. This is part of why Claude tends to be
fluent at recognizing common patterns (a `for` loop, a SQL `JOIN`, a
regex) — it has seen enormous numbers of near-identical structures — but
can be less reliable on unusual formatting, deeply nested logic, or
whitespace-sensitive edge cases, where the token-level pattern-matching has
less to anchor on.

**"Explaining code" and "generating code" are the same underlying process
run in different directions.** Explaining is generation conditioned on the
code as input context (the model attends to your snippet and produces
natural-language tokens); generating a script is the reverse — natural
language conditioning producing code tokens. Neither one involves actually
*running* the code unless the product you're using has an explicit
code-execution tool attached. This is the mechanistic reason a plausible
explanation, or plausible-looking generated code, can still be subtly wrong
about behavior: the model is producing what a correct explanation or a
working script would statistically look like, not tracing an actual
execution.

**This is exactly why the "safety habit" of testing on a copy matters.**
Because nothing was executed during generation, "looks right" and "is
right" are only loosely correlated for code — the model has no built-in
feedback loop confirming its own output actually behaves the way it reads.
Only running it (or having a tool do so) closes that loop.

## Exercise

Think of a repetitive task you do manually that a small script or formula
could plausibly handle (renaming files, flagging rows in a spreadsheet,
reformatting data). Write a generation prompt that describes the goal
precisely and explicitly asks for an explanation and a note on risks. If you
have access to Claude, try it, and write down one thing in its explanation
you would double check before actually running it.
