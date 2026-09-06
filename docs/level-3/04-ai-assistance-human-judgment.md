# 04 · Combining AI Assistance with Human Judgment

Every prior module has implied a boundary between what Claude should
generate and where a human needs to decide, verify, or take
responsibility. This module makes that boundary explicit and gives a
framework for drawing it deliberately rather than by accident.

## The core distinction: generation vs. judgment

Claude is strong at generation — producing drafts, options, structured
extractions, and analysis quickly across a wide range of tasks. It is not
a substitute for judgment that requires: accountability for the outcome,
values-based tradeoffs specific to your situation, knowledge of context
it wasn't given, or responsibility for the consequences of being wrong.
Good AI-assisted work uses Claude heavily for the first category and never
delegates the second.

## A framework: who decides what

| Category | Claude's role | Human's role |
|---|---|---|
| Drafting/structuring | Do the heavy lifting | Review and redirect |
| Factual claims | Flag confidence, cite what it can | Verify before relying on it |
| Judgment calls with real stakes (a hire, a legal position, a medical or financial decision) | Lay out considerations and tradeoffs | Make and own the actual decision |
| Values/priority tradeoffs specific to your situation | Can surface the tradeoff | Must resolve it — Claude doesn't know your actual priorities unless told, and even then isn't accountable for them |
| Anything where being wrong is costly and hard to reverse | Can help you think it through | Final sign-off always human |

## Signs you're over-delegating

- Accepting a recommendation without being able to say *why* it's right —
  if you can't explain the reasoning yourself, you haven't actually
  reviewed it, you've deferred to it.
- Using Claude's confidence as a proxy for correctness. Fluent, decisive
  phrasing is not evidence of being right (see Module 6/9 in Level 2).
- Skipping the verification step under time pressure specifically for the
  claims that matter most to the outcome — the moment you're in a hurry is
  exactly when this shortcut is most tempting and most risky.

## Signs you're under-using it

- Manually doing structuring, drafting, or first-pass analysis that Claude
  could produce in seconds, then spending your judgment budget on
  formatting instead of on the actual decision.
- Treating every output as needing the same level of scrutiny regardless
  of stakes — a low-stakes internal draft doesn't need the same
  verification rigor as a client-facing claim.

## A practical pattern: draft-then-own

For decisions with real weight, a reliable pattern is: use Claude to lay
out the options and tradeoffs as thoroughly as possible, then step away
from the screen and make the actual call yourself, in your own words,
citing your own reasons — even if those reasons closely echo what Claude
surfaced. This isn't a formality: articulating the decision yourself is
where you catch a tradeoff that doesn't actually apply to your situation,
or a consideration that matters more than Claude's framing suggested.

> "Lay out the tradeoffs between these two vendors as thoroughly as you
> can — cost, risk, switching cost, fit with our existing tools. Don't
> recommend one; that call is mine to make once I've seen the tradeoffs
> clearly."

Explicitly asking Claude *not* to recommend, when the decision is yours to
own, keeps the tool in its lane and keeps you actually engaging with the
tradeoffs rather than anchoring on a suggested answer.

## Documenting where judgment was applied

For decisions that will be reviewed or questioned later, note briefly
where Claude's output ended and human judgment took over — e.g., "options
and cost estimates drafted with AI assistance; final vendor choice and
risk tolerance decision made by [name] based on [specific reason]." This
isn't bureaucracy for its own sake — it's what lets you (or anyone else)
reconstruct the reasoning later, and it keeps accountability clear.

## How It Actually Works

The generation-vs-judgment boundary isn't just a practical convenience —
it maps onto a real gap between what the underlying mechanism can and
cannot supply, no matter how good the prompt is.

**Generation draws on patterns present in training data and whatever's in
context — it has no access to information that exists only in your head or
in the future.** A model producing a draft, a structured extraction, or an
analysis is recombining and applying statistical patterns learned from
text plus whatever you've supplied in the current context window. Values-
based tradeoffs specific to your situation, accountability for the
outcome, and knowledge that was never written down anywhere Claude could
have learned it or that you didn't supply are, by construction, not
present in that context — no amount of clever prompting manufactures
information or authority that was never given to the model.

**This is why "over-delegating" has a specific mechanistic signature: it
means letting fluent, confident generation stand in for a decision that
actually depended on facts or values outside context.** Because fluency and
correctness are optimized somewhat independently (Module 9, Level 1), a
generated recommendation can read exactly as confidently whether or not it
accounts for the constraint that only you knew about — there's no internal
signal distinguishing "I have everything I need to say this" from "this is
the most plausible-sounding thing to say given what I have," which is
precisely the gap human judgment has to fill.

**The draft-then-own pattern works by using generation for what it's
mechanistically good at (producing a well-formed starting point fast) while
keeping the review step for what it's not good at (judging against
context the model never had).** This isn't a compromise so much as
matching each half of the task to the part of the system suited to it: the
model's strength is breadth and speed of plausible generation conditioned
on what's given; your strength is knowing what wasn't given and what it's
actually worth.

## Exercise

Think of a recent decision where you used Claude's output heavily. Using
the framework table, identify which parts were legitimately generation
(fine to lean on fully) and which were actually judgment calls you may
have deferred more than you should have. Write one sentence stating the
judgment call in your own reasoning, independent of how Claude framed it.
