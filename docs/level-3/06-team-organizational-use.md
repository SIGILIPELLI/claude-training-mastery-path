# 06 · Team/Organizational Use of AI Assistants

Moving from individual use of Claude to a team using it consistently
introduces problems that don't exist for a single user: inconsistent
quality, duplicated effort building the same prompts, and no shared
standard for what's safe to paste into a prompt. This module covers how to
scale good practice across a team.

## Why individual best practice doesn't automatically scale

One person can hold "always verify specific claims" and "don't paste
customer PII into a prompt" in their head. A team of twenty can't rely on
everyone independently having internalized the same discipline — some
will, some won't, and the failures will be inconsistent and hard to trace.
Scaling requires making the good practice the path of least resistance,
not just documented advice.

## Shared prompt/persona libraries

Rather than each person re-deriving a persona for a common task (Level 2,
Module 8), maintain a small shared library of vetted, tested prompts and
personas for the team's recurring tasks — status report drafting, code
review checklists, meeting summarization — with:

- The prompt/persona itself
- What it's for and what it's *not* for
- Who tested it and against what inputs (Module 3's test-set discipline)
- A named owner who updates it when it stops working well

A shared library also means an improvement one person makes benefits
everyone, instead of staying siloed in their own habits.

## Setting a data-handling baseline

Before broad team adoption, establish and communicate a clear, simple
rule for what's acceptable to paste into a prompt — this is covered in
depth in Module 7, but at the team level it needs to be a stated policy,
not an individual judgment call, since a single person's mistake with
sensitive data affects the whole organization's risk, not just theirs.

## Consistency without killing individual judgment

The goal isn't to force everyone into identical prompts — it's to prevent
avoidable inconsistency on things that matter (safety, accuracy
verification, format for shared deliverables) while leaving room for
individual style on things that don't. A good split:

| Standardize | Leave flexible |
|---|---|
| Data handling rules | Personal brainstorming style |
| Verification requirements for anything going external | Which interface someone prefers for drafting |
| Shared deliverable formats (so outputs are consistent across the team) | Internal note-taking prompts |

## Onboarding new team members

A short, concrete onboarding beats a long policy document: show 2-3 real
before/after examples of a prompt that failed and the fixed version, point
to the shared library, and state the data-handling rule plainly. People
learn the actual failure modes (fabricated facts, leaked sensitive data,
inconsistent formats) faster from real examples than from abstract
guidance.

## Reviewing AI-assisted work at the team level

For deliverables produced with heavy AI assistance that go external or
inform a real decision, a lightweight review norm helps: the person who
produced it states what was verified and what wasn't (Level 2 Module 6,
Level 3 Module 4), and a second person spot-checks before it goes out —
the same principle as code review, applied to AI-assisted analysis and
writing.

## Measuring whether it's working

Signs the team-level practice is working: fewer repeated "I didn't know
you weren't supposed to paste that" incidents, less duplicated prompt
engineering across people doing the same task, and consistent quality on
shared deliverables regardless of who produced them. Signs it isn't: the
shared library exists but nobody uses it (usually a sign it's not
actually easier than writing from scratch), or verification is happening
inconsistently depending on who's under deadline pressure that week.

## How It Actually Works

Shared prompt libraries and standards aren't just organizational hygiene —
they compensate for a real property of the underlying mechanism: prompts
are not portable "settings," they're the literal content the model
conditions on, so every rewrite is a fresh roll of the dice.

**Two people describing "the same task" produce meaningfully different
context, and therefore meaningfully different output distributions.**
Because output quality is driven by exactly what tokens are present —
clarity, context, specificity (Module 2, Level 1) — one teammate's careful,
specific phrasing and another's rushed, vague version of "the same"
request are, mechanistically, different conditioning inputs, and there's
no reason to expect the same quality of output from them. This is the
literal cause of "inconsistent quality" across a team: it's not that some
people are better at getting Claude to cooperate, it's that they're
supplying it different information to condition on.

**A shared library works the same way a personal template does (Module 10,
Level 1), scaled up** — it fixes the highest-leverage tokens (role, format,
constraints, data-handling boundaries) once, centrally, so that variation
across team members' usage collapses to just the task-specific inputs
they drop in, rather than variation in the entire prompt.

**A data-handling baseline matters because context, once sent, is context
the model has processed** — there's no mechanism for retroactively
un-conditioning a response on information already included in a request.
This is exactly why the practical rule is about what goes into the prompt
in the first place, not about anything that could be done afterward.

## Exercise

For your own team (or a hypothetical one doing similar work), draft: one
data-handling rule stated in one sentence, and one shared persona for a
task at least two people on the team do regularly. Test the persona
against inputs from a second person, not just your own — note whether it
holds up on inputs you didn't personally design it around.
