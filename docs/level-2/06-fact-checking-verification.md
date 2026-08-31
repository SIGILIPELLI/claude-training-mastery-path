# 06 · Fact-Checking & Source Verification Workflows

Level 1 introduced the core caution: verify anything Claude states as
fact before you rely on it. This module builds that into a repeatable
workflow — how to ask Claude to help you verify, what it can and can't
verify for itself, and how to structure a verification pass so nothing
slips through.

## Claude cannot verify against reality on its own

Without a live tool (search, a connected document, a database), Claude is
generating text from patterns learned in training — it has no way to check
a specific claim against the current state of the world at the moment
you're talking to it. This means:

- Specific numbers (statistics, prices, dates, version numbers) are the
  highest-risk category — they're precise-sounding but easy to get subtly
  wrong or out of date.
- Named sources (a specific study, a specific law, a specific person's
  stated position) are the second-highest risk — Claude can produce a
  plausible-sounding citation that doesn't actually exist or doesn't say
  what's claimed.
- General, stable, well-known information (how a common process works, a
  widely-documented technical concept) is lower risk, but "lower" is not
  "zero."

## Asking Claude to flag its own uncertainty

You can ask Claude to distinguish, in its own output, between what it's
confident is stable/well-known and what it's less sure of or where it's
extrapolating:

> "Answer this, but mark any specific number, date, or named source with
> [VERIFY] so I know exactly what to double-check before I use this."

This doesn't make the underlying claims more accurate, but it turns a wall
of undifferentiated text into a short, actionable checklist of things to
verify — much cheaper than fact-checking every sentence equally.

## A verification workflow for research or writing tasks

1. **Get the draft or answer.**
2. **Extract the checkable claims.** Ask: "List every specific factual
   claim in this — numbers, dates, named studies/sources, quotes — as a
   numbered list, one claim per line, with no analysis."
3. **Verify each independently**, using a real source (a search, an
   official document, the primary source itself) — not by asking Claude
   again, since a repeated question can produce a repeated, equally
   ungrounded answer.
4. **Correct or cut** anything that doesn't hold up, and note anything you
   couldn't verify in the time available so you don't forget it was
   unconfirmed.

## When Claude has real source material to work from

If you paste in the actual source document, transcript, or dataset, ask
Claude to ground every claim in that pasted material specifically —this
is a meaningfully different and more reliable case than an open question:

> "Everything in your answer must be traceable to the document below.
> After each claim, cite the exact sentence or section it's based on. If
> something isn't in the document, say 'not stated in source' rather than
> filling the gap from general knowledge."

This still requires spot-checking, but it constrains the task from "does
Claude know this fact" to "did Claude read this text correctly" — the
latter is a much easier and more checkable task.

## Red flags that a claim needs closer scrutiny

| Signal | Why it's risky |
|---|---|
| A suspiciously precise number ("73.4% of companies...") with no source named | Precision without provenance is a common fabrication pattern |
| A quote attributed to a specific person or document | Quotes are exactly the thing worth checking verbatim, word for word |
| A claim that conveniently supports the point you asked Claude to argue for | Motivated framing can shade a claim even when Claude isn't intentionally biased |
| Anything time-sensitive (current prices, current staff, current law) | Training data has a cutoff and the real world keeps moving |

## Building the habit into a team workflow

For recurring outputs used in decisions (a competitive analysis, a report
circulated externally), make the verification step a named part of the
process rather than an individual's optional judgment call — e.g. a
"claims checked" checkbox before anything goes out, with the checker named.
Module 8 in this level covers building this kind of habit into repeatable
personas/instructions.

## Exercise

Take a piece of Claude output (yours or a sample) that includes at least
three specific factual claims. Run the four-step verification workflow:
extract the claims as a numbered list, verify each against a real source,
and produce a corrected version noting anything you couldn't confirm.
