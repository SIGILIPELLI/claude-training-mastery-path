# 02 · Using AI for Complex Multi-Step Workflows

This module covers designing workflows where Claude handles several
distinct stages of a real process — not one prompt, but a pipeline with
checkpoints, handoffs, and places where a human reviews before the next
stage proceeds.

## Why multi-step beats one giant prompt

A single prompt asking for a complex end-to-end outcome ("research this
market, write a go-to-market plan, and draft the launch emails") forces
Claude to make dozens of implicit judgment calls with no chance for you to
correct course. Breaking it into stages gives you a review point after
each one, where a wrong turn costs you one stage of rework instead of the
whole thing.

## Designing a workflow: stages, inputs, and gates

A well-designed multi-step workflow specifies, for each stage:

- **Input**: what feeds into this stage (raw material, or the output of
  the previous stage)
- **Task**: the specific, narrow job for this stage
- **Output shape**: exactly what should come out
- **Gate**: what you check before letting it proceed to the next stage

**Example — turning research into a client deliverable:**

| Stage | Input | Task | Gate |
|---|---|---|---|
| 1. Research | Raw sources | Extract findings as a table with confidence levels | Are the [VERIFY]-flagged claims actually checked? |
| 2. Synthesis | Verified findings | Draft key takeaways, 3-5 bullets | Do the takeaways follow from the findings, not from assumption? |
| 3. Draft | Takeaways | Full first draft of the deliverable | Is the structure right before polishing prose? |
| 4. Polish | Draft | Tighten language, check tone/audience fit | Final read before it goes out |

## Handing off between stages cleanly

When a stage's output feeds the next stage's input, be explicit about what
carries forward and what to ignore, so Claude doesn't re-derive or
re-litigate an earlier stage's decisions:

> "Using only the verified findings table below (not any other
> assumptions), draft the takeaways. Do not revisit which claims were
> verified — treat this table as settled."

## Parallel vs. sequential stages

Some stages are genuinely independent and can run in parallel (e.g.
drafting three unrelated sections of a report from the same source
material); others are strictly sequential because each depends on the
previous one's actual output (e.g. you can't polish a draft that doesn't
exist yet). Design the workflow around the real dependency structure:
running independent stages in parallel saves time; forcing a sequential
dependency into parallel work produces stages that don't actually fit
together.

## Where humans stay in the loop

For any workflow feeding a real decision or external deliverable, decide
in advance which gates require actual human review (not just glancing at
it) versus which can be trusted to proceed automatically:

- **Always review**: anything going external, anything involving a
  factual claim used in a decision, anything hard to undo once sent.
- **Spot-check**: repetitive, low-stakes stages once you've validated the
  pattern holds (e.g. after checking the first five outputs of a
  templated extraction match the source correctly).
- **Full autonomy reasonable**: purely mechanical reformatting of already
  -verified content, where an error would be immediately obvious.

## Recovering when a stage goes wrong

Multi-step workflows should make failure cheap to isolate: if stage 3's
output is wrong, go back to stage 3 with a correction, not back to stage
1. This is the practical payoff of designing gated stages in the first
place — you know exactly where to intervene.

> "Stage 3 draft assumed the wrong target audience. Redo stage 3 only,
> using the same verified findings and takeaways from stages 1-2, but
> targeting [correct audience] instead."

## How It Actually Works

Why does splitting a complex task into stages reliably beat one giant
prompt, beyond "it's easier to review"? The mechanism is about how errors
propagate through generation, and how much any single prediction has to
get right at once.

**A single giant prompt asks for one very-high-dimensional prediction.**
"Research this market, write a plan, and draft the emails" compresses many
independent judgment calls into one continuous generation — market
findings, strategic reasoning, and email tone are all being decided
simultaneously, conditioned on each other, with no checkpoint where an
early wrong turn (a mis-scoped market finding, say) gets corrected before
it becomes conditioning for everything downstream. Once "the market is
X" appears early in that single response, everything generated after
attends to it as if it were established fact, compounding any early error.

**Staged pipelines convert one hard prediction into several easier,
verified ones chained together.** Each stage's output, once you've
reviewed and corrected it, becomes clean, human-checked context for the
next stage's prompt — rather than unverified, self-generated context the
model produced moments earlier in an uninterrupted response. This is the
same principle as chain-of-thought (Module 2, Level 2), but with a human
review gate inserted between steps instead of letting the model's own
next reasoning step build on a still-unverified prior step.

**Parallel stages work when their inputs don't depend on each other's
output, because each one is an independent context assembly with nothing
to inherit from a sibling stage** — running them concurrently doesn't
change the per-stage mechanism at all, it just reflects that stage B's
prompt doesn't need anything stage A generated to be well-formed.
Sequential stages are required precisely when a later prompt's context
must include an earlier stage's verified output to be well-grounded.

**Recovering from a failed stage is cheap for exactly the reason a single
giant prompt's failure is expensive:** because each stage is a bounded,
separately-conditioned generation, a bad result is contained to what was
built on top of *that stage's* output, not the entire chain — you re-run
one prompt with corrected context rather than regenerating everything from
one contaminated context.

## Exercise

Take a real multi-part task you currently do in one long back-and-forth
with Claude. Redesign it as an explicit staged workflow: list each stage's
input, task, output shape, and gate. Run it staged instead of all at once,
and note where a gate actually caught something you'd have missed doing
it in one pass.
