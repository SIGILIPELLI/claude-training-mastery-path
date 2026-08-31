# 10 · Project — A Multi-Step Research Workflow Using Claude

This capstone ties together every Module 1-9 technique into one repeatable
research workflow: a multi-step process for researching a real question,
producing a structured, verified output you could actually hand to
someone else.

## The scenario

Pick a real research question you'd genuinely benefit from answering —
something with enough substance to need multiple steps, e.g.: "Should our
team adopt [tool/process X]?", "What are the tradeoffs between three
specific options for [a real decision]?", or "What does our competitor's
recent [product change] mean for us?" Avoid a toy question — the exercise
only teaches you something if the output has to actually be good enough to
use.

## Step 1: Scope the question (Level 1 clarity + Module 1 output contracts)

Before asking for content, ask Claude to help scope the question itself:

> "I want to research [question]. Before we start, help me scope it: what
> are the 3-4 sub-questions this really breaks into? What would a useful
> final answer need to include to actually support a decision?"

Review the sub-questions — cut any that don't matter for your actual
decision, add any Claude missed that you know matter.

## Step 2: Research each sub-question with structured output (Modules 1, 3, 4)

For each sub-question, ask for a structured extraction rather than prose,
and mark uncertain claims per Module 6:

> "For sub-question 2 ([...]), give me what's known as a table: Claim,
> Confidence (High/Medium/Low), and mark anything specific — a number,
> date, or named source — with [VERIFY]."

## Step 3: Verify the flagged claims (Module 6)

Pull out every `[VERIFY]` item into its own list and check each against a
real source — not by re-asking Claude. Note next to each: confirmed,
corrected, or unconfirmed (and why).

## Step 4: Brainstorm implications or options (Module 5)

With the research in hand, brainstorm what it implies, using explicit
categories to force range rather than the first obvious take:

> "Given this research, brainstorm what we could actually do about it.
> Cover at least: a low-cost/low-risk option, a higher-investment option,
> and a 'do nothing yet, but monitor X' option."

## Step 5: Chain-of-thought synthesis into a recommendation (Module 2)

> "Walk through this in order: (1) what does the verified research
> actually support, (2) which of the options from step 4 best fits our
> actual constraints [state them], (3) what's the single biggest risk of
> that choice, (4) recommendation. Don't skip to (4)."

## Step 6: Final structured deliverable (Module 4)

Ask for the whole thing assembled into one document with a fixed shape you
specify — e.g.:

> "Assemble everything above into one document: Executive Summary (3
> sentences max), Key Findings (table, with confidence and verification
> status), Options Considered, Recommendation, Open Risks/Unknowns. Use
> `##` headings."

## Step 7: Self-review pass (Modules 6, 9)

Before treating it as done, run one more check:

- Every specific claim in the final document — is it marked with its
  verification status, and did you actually check the ones marked
  uncertain?
- Does the recommendation follow from the findings above it, or does it
  jump somewhere the findings don't support?
- Is anything stated more confidently than the underlying evidence
  justifies?

## Deliverable

A finished research document produced through the workflow above, plus a
short log (a few lines is enough) of: which claims you verified and how,
what you corrected or removed, and one thing the workflow caught that a
single-shot "research this for me" prompt would likely have missed.

## What this project should make visible

Doing this end-to-end usually surfaces two things: how much a *sequence*
of narrow, checkable steps beats one broad ask, and how much of the actual
value is in the verification and review steps rather than the generation
steps — the parts that are easiest to skip under time pressure are the
ones that matter most for anything you'll actually rely on.
