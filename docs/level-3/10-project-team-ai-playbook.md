# 10 · Project — Design a Team AI Usage Playbook

This capstone ties together Level 3's modules into a single deliverable:
a written playbook your team (real or hypothetical) could actually use to
adopt AI assistance consistently, instead of everyone improvising their
own approach.

## The scenario

Pick a real team you're part of, or a realistic one you know well —
enough specificity that the playbook has to hold up against actual
workflows, tools, and constraints, not generic advice. A playbook written
for "a team" in the abstract teaches nothing; a playbook written for
"the 6-person support team using Zendesk and Slack" forces real
decisions.

## Step 1: Inventory current use (Module 6)

Before prescribing anything, find out what's actually happening:

> "Here's a rough list of the tasks my team does where AI assistance
> could help: [list]. For each, help me think through: is this already
> being done with AI informally, and what would a repeatable version of
> that look like?"

Talk to a few teammates if this is a real team — the playbook should
describe what people need, not what you assume they need.

## Step 2: Define shared context management (Module 1)

Decide how the team will handle context for recurring work: is there a
shared prompt/template library (Level 1, Module 10), a standard set of
background docs to paste in, a convention for what goes in a project-
level system prompt vs. what's re-stated per request? Write this down as
a short standard, not a discussion.

## Step 3: Set the privacy/data boundary (Module 7)

State explicitly, in the playbook itself, what categories of data are
never pasted into an AI tool (customer PII, credentials, unreleased
financials — whatever applies to your team), and what the approved tool
and account setup is. Ambiguity here is the most common way teams get
into trouble.

## Step 4: Define the human-judgment checkpoints (Module 4)

For each task type from Step 1, specify where a human reviews before
output goes anywhere external: what gets fully reviewed, what gets spot-
checked, and what (if anything) is low-stakes enough to ship without
review. Be specific — "review as needed" is not a standard anyone can
follow consistently.

## Step 5: Build one repeatable process end-to-end (Module 8)

Pick the single highest-volume task from your inventory and write it out
as a full repeatable process: the prompt template, the inputs it needs,
the verification step, and the output format. This is the part of the
playbook other people will actually copy first.

## Step 6: Add a quality bar (Module 9)

Include a short rubric (3-5 lines) for what "good" looks like for your
team's most common AI-assisted output, so reviewers aren't each applying
a different unstated standard.

## Step 7: Write the rollout note

Add a short section (a few sentences) on how this playbook gets
introduced to the team: who owns keeping it updated, how someone
proposes a change, and where it lives.

## How It Actually Works

Building a team playbook is really an exercise in institutionalizing the
mechanism-level lessons from every module in this level, so it's worth
naming the thread that ties them together.

**Every step you're documenting is really a decision about what context
gets assembled, how, and who checks the result.** Inventorying current
use (Step 1) surfaces where teammates are supplying inconsistent context
for "the same" tasks (Module 6's core problem); shared context management
(Step 2) fixes that by centralizing the highest-leverage tokens once;
the privacy boundary (Step 3) governs what's allowed into that shared
context at all, because once sent, it's processed and potentially retained
regardless of intent (Module 7); the human-judgment checkpoints (Step 4)
mark exactly the points where the task depends on information or
accountability the model was never given (Module 4); and the quality bar
(Step 6) operationalizes the fluency-versus-correctness gap (Module 9) as
an explicit, checkable rubric rather than a vague "looks right."

**A playbook is durable precisely because it doesn't depend on any one
person recreating good context from memory each time** — it's the team-
scale version of the repeatable process from Module 8: documented inputs,
framing, and verification steps that produce consistent conditioning for
the model regardless of who runs them or when.

## Deliverable

A single document (1-3 pages is plenty) covering: current-use inventory,
context-management standard, data/privacy boundary, review checkpoints,
one fully worked repeatable process, a quality rubric, and an ownership
note. Share a draft with at least one teammate before calling it final —
a playbook nobody else read is still just your personal notes.

## What this project should make visible

Writing this down usually surfaces disagreements that were invisible
while everyone was working alone — different assumptions about what's
safe to paste in, different bars for what counts as "reviewed." Making
those explicit is the actual value of a playbook; the AI-specific
content is almost secondary to the fact that the team now has one shared
answer instead of several unstated ones.
