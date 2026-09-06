# 02 · Chain-of-Thought & Step-by-Step Reasoning Prompts

Claude, like other LLMs, produces more reliable answers on multi-step
problems when it reasons through the steps explicitly rather than jumping
straight to a conclusion. This module covers when and how to prompt for
that reasoning, and how to read it critically.

## Why asking for steps helps

A direct question ("Should we migrate to microservices?") invites Claude to
pattern-match to a plausible-sounding answer. A question that asks for the
reasoning path forces it to lay out the actual considerations in order,
which:

- surfaces assumptions you can check or correct before accepting the answer
- catches arithmetic and logical errors that a jump-to-conclusion answer
  would hide
- gives you a partial answer to work with if the full chain isn't quite
  right — you can fix step 3 instead of discarding the whole response

This matters most for math, multi-step logic, planning, and any decision
with several interacting factors. It matters least for tasks that are
mostly retrieval or style (e.g. "rewrite this in a friendlier tone") —
asking those to "think step by step" just adds noise.

## Basic pattern

> "A team of 6 can finish a project in 15 days. After 5 days, 2 people are
> reassigned. How many total days will the project take? Work through the
> math step by step before giving the final answer."

Without the instruction, Claude may still show some work, but explicitly
asking for it makes the steps more complete and more likely to be checked
against each other before the final line is written.

## Structuring the steps yourself

For workflows you repeat, don't just say "think step by step" — specify
*which* steps, so the reasoning follows a path you trust instead of
whatever order Claude picks.

**Generic:**
> "Should we approve this vendor? Think it through step by step."

**Structured:**
> "Evaluate this vendor proposal in this order: (1) does it meet our
> stated technical requirements — list any gaps, (2) total cost over 3
> years including hidden fees, (3) contract risk — auto-renewal,
> termination penalties, data ownership, (4) your recommendation with the
> single biggest factor driving it. Do not skip to (4) without completing
> 1-3."

The structured version is more useful because a bad recommendation is easy
to spot when you can see which of the four steps it disagrees with.

## Decomposition for multi-part problems

For problems with independent sub-parts, ask Claude to solve each part
separately before combining them, rather than reasoning about everything
at once.

| Problem type | Decomposition |
|---|---|
| Pricing a bundle of services | Price each service standalone → identify overlap/discount logic → compute bundle price → sanity-check against a competitor price point |
| Debugging a failing test | State what the test expects → state what the code actually does → identify the exact line where they diverge → propose the fix |
| Planning a launch | List dependencies → order by dependency → assign realistic durations → flag the critical path |

## Self-checking: asking Claude to verify its own chain

A second, cheap technique: after Claude produces a chain of reasoning, ask
it to check its own work before you accept it.

> "Review the reasoning above. Is there a step where the logic doesn't
> follow, a number that doesn't add up, or an assumption that's stated but
> never justified? List any issues, then give a corrected final answer if
> needed."

This isn't infallible — a model can miss its own error on a second pass —
but it catches a meaningful share of arithmetic slips and unjustified
leaps, and it's nearly free to ask for.

## What chain-of-thought does *not* fix

Reasoning transparency helps you catch errors, but it doesn't guarantee
correctness. Watch for:

- **Confident wrong steps.** A clearly-written step 3 can still be false.
  Fluency isn't accuracy — read each step, don't just skim for structure.
- **Missing information problems.** If the real answer depends on a fact
  Claude doesn't have (your actual inventory levels, a number buried in a
  document you didn't paste), no amount of step-by-step reasoning invents
  that fact correctly. Give Claude the data, don't ask it to guess plausibly.
- **Padding.** Sometimes "think step by step" produces steps that restate
  the question rather than genuinely decompose it. If the steps aren't
  adding information, tighten the prompt to name the actual sub-questions.

## How It Actually Works

Chain-of-thought prompting is one of the clearest places where understanding
the generation mechanism explains *why* a prompting technique works, rather
than just that it does.

**Each reasoning token becomes conditioning for the tokens after it.**
Autoregressive generation means every new token is predicted from
everything already generated, including the model's own prior output in
this same response. When Claude writes out "Step 1: current team size is
X, Step 2: their velocity is Y, therefore..." each of those intermediate
statements becomes part of the input the *next* token is conditioned on. A
jump-straight-to-the-answer response has none of that intermediate
scaffolding to condition on — it has to get the right answer in one
uninterrupted burst of plausibility, with no opportunity to "correct
course" partway through the way explicit steps allow.

**This is why decomposition helps with multi-part problems specifically.**
A complex question compresses many sub-decisions into one generation
target, and without explicit steps, the model has to implicitly juggle all
of them under one probability distribution at once, which is much easier to
get partially wrong. Breaking it into named sub-questions turns one hard,
high-dimensional prediction into several easier, lower-dimensional ones
chained together — each step's output becomes clean, explicit context for
the next.

**Self-checking works by making the model generate a *second*, differently-
framed pass over the same material, which surfaces a different set of
plausible continuations.** Asking "check your work" doesn't grant access to
some hidden verification module — it simply runs the same
next-token-prediction machinery again, now conditioned on the original
answer plus an instruction to scrutinize it, which the training data
associates with more cautious, error-catching language. It catches some
mistakes because that reframing shifts the distribution, not because
there's now a guaranteed-independent check.

**What it doesn't fix, and why:** chain-of-thought cannot compensate for
missing facts, because generated reasoning tokens are still produced from
the same training-data patterns and whatever's in context — if the true
answer depends on information the model was never given, no amount of
step-by-step scaffolding manufactures that information. It also doesn't
guarantee the *displayed* reasoning caused the *displayed* answer in a
strictly causal sense — a fluent-looking derivation can still be
post-hoc-plausible rather than the actual determining factor, which is
exactly why verification (Module 9, Level 1) still matters even when
Claude "shows its work."

## Exercise

Take a decision you're currently weighing (a purchase, a process change, a
technical approach) that has at least three factors feeding into it. Write
a structured, step-ordered prompt that names each factor explicitly and
asks for the recommendation last. Then write a one-line self-check prompt
and run it against the output. Note whether the self-check changed the
answer.
