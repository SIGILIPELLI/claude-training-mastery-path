# 06 · Staying Current as AI Capabilities Evolve

AI capabilities change faster than most software, which creates a real
risk this course tries to avoid: teaching version-specific tricks that
go stale, or worse, letting readers assume today's limitations are
permanent constraints to design around forever. This module is
deliberately about durable habits for staying current, not about any
specific current capability — those change; the habit of tracking them
doesn't.

## The mistake: treating today's limits as permanent

Every generation of AI tools has had capabilities that improved faster
than expectations updated — context window size, reliability on
multi-step tasks, tool use. Workflows built around "AI can't do X" often
outlive the actual limitation, because habits are stickier than facts.
The practical implication: periodically re-test assumptions you've been
working around, rather than assuming a past limitation is still true.

## What actually needs re-checking periodically

- **Assumptions baked into your templates and processes** (Level 3,
  Module 8) — a workaround for a limitation that no longer exists is
  now just unnecessary extra work.
- **The point where you stopped trusting AI on a given task type** —
  worth an occasional spot-check rather than a permanent verdict.
- **What's now safe to do in fewer steps** — a multi-step workflow
  (Level 3, Module 2) built around a past constraint may be
  compressible.

## A sustainable way to stay current, without doom-scrolling AI news

Chasing every announcement is not a sustainable habit and mostly adds
noise. A lighter approach that actually holds up:

1. Pick one or two sources you trust for substantive changes (not hype)
   and check them on a fixed light cadence rather than continuously.
2. When you learn a real capability changed, test it on one of *your*
   actual recurring tasks before updating any workflow — a general
   announcement doesn't tell you how it behaves on your specific case.
3. Update the shared template or process (not just your personal
   habit) when a change is confirmed to matter, so the org-level
   capability from Module 1 stays current too, not just your own.

## Skepticism in both directions

Apply the same evaluative habits from Level 3, Module 9 to claims about
new capabilities as you would to any other AI output: a bold claim about
a new capability deserves the same "verify before trusting" treatment as
any other confident-sounding claim, and an old limitation deserves an
occasional re-test rather than being assumed permanent. Both errors — 
believing every new claim, and never updating an old assumption — cost
real time.

## How It Actually Works

The durable/perishable split this course draws throughout is itself
grounded in a mechanistic distinction worth making explicit: some things
about these systems are properties of the architecture (durable), and some
are properties of a specific trained model or product (perishable).

**Durable facts are about the mechanism itself — tokens, context windows,
attention, autoregressive generation, sampling — which don't change just
because a new model ships.** A newer, larger, better-trained model is still
predicting the next token from context via attention; the qualitative
reasons that specificity narrows output, that long conversations dilute
early instructions, or that fluency and correctness are only loosely
correlated all still apply, even as the *quantitative* specifics (how long
a context window is, how good the model is at holding onto material within
it, how often it hallucinates on a given kind of task) improve.

**Perishable facts are about a specific model's or product's current
performance envelope — context window size, benchmark scores, which
specific mistakes it's prone to — which are exactly the things that
improve fastest and go stale fastest.** Treating today's specific
limitation as a permanent constraint to design around is the direct
mistake this module names, and it's a mistake precisely because it
confuses a snapshot of current capability with a fact about how the
mechanism works — the two categories require different amounts of
re-checking, which is why this section itself avoids citing specific
numbers that would be exactly this kind of perishable claim.

## Exercise

List one workflow or habit you built around a past limitation of AI
tools. Re-test that specific limitation today, on a real example, and
record the actual result — not what you assume it would be, and update
(or explicitly keep) the workflow based on what you find.
