# 03 · Responsible AI Use & Governance Basics

Level 3 covered personal data-handling discipline. At an organizational
scale, that discipline needs to become governance: written policy,
assigned ownership, and a process for handling the cases individual
judgment alone won't reliably get right. This module covers the basics
of what that governance needs to include, without requiring you to be a
policy specialist.

## What governance is actually for

Governance exists to make three things consistent across an
organization instead of left to individual interpretation: what data
can go into an AI tool, what output requires human review before it's
used externally, and who is accountable when something goes wrong. None
of these need to be complicated, but all three need to be *written down
and owned* — an unwritten norm that "everyone knows" is not governance,
it's a shared assumption that breaks the first time someone new joins.

## The minimum viable policy

A working AI-use policy, even a short one, should answer:

| Question | Example answer |
|---|---|
| What data may never be entered into an AI tool? | Customer PII, credentials, unreleased financials, anything under NDA |
| Which approved tools/accounts should be used? | Named tools with the org's data-handling terms, not personal accounts |
| What output must be human-reviewed before external use? | Anything sent to a customer, published, or used in a decision with real stakes |
| Who owns this policy and updates it? | A named role, not "IT" in the abstract |
| How does someone report a concern or a near-miss? | A named channel, checked regularly |

A one-page version of this, actually read and followed, beats a
thorough policy nobody can find.

## Accountability without paralysis

Good governance assigns responsibility for *outcomes*, not for every
individual AI-assisted action — the goal is not to require sign-off on
every use of AI, which nobody will sustain, but to make clear that a
human is accountable for anything that reaches a customer, a decision,
or the public, regardless of how it was drafted. That accountability
doesn't change because a tool helped write the first draft.

## Common governance gaps

- **No policy on vendor/third-party AI tools** embedded in other
  software the org already uses, which often handle data without
  anyone having reviewed the terms.
- **No incident process**: when something does go wrong (a factual
  error reaches a customer, sensitive data gets pasted somewhere it
  shouldn't), there's no defined next step, so it either gets buried or
  handled inconsistently.
- **Policy written once and never revisited** as tools and use cases
  change — governance needs an owner and a review cadence, not a launch
  date.

## How It Actually Works

Good governance policy is written around two hard mechanistic facts about
how these systems actually behave — worth stating explicitly so policy
doesn't drift into rules that don't match reality.

**Inputs are processed and potentially retained the moment they're sent —
there's no "undo" once a prompt is submitted.** As covered in Module 7
(Level 3), the tokens in a request are computed over immediately and may
be logged or retained per the provider's policy; a governance policy that
tries to control data handling *after the fact* is solving the wrong
problem — the only point of control that actually exists is what's allowed
into the prompt (or a connected tool's reach) in the first place, which is
why minimum viable policy centers on pre-submission rules, not
post-submission remediation.

**Output correctness is not guaranteed by the mechanism, so accountability
for a wrong output has to sit with a person, not the tool.** Because
generation optimizes for plausibility rather than verified truth (Module 9,
Level 1), there is no meaningful sense in which "the AI" can be
accountable for a bad decision made using its output — accountability
requires a state of knowing and choosing that only a person using the tool
has. This is the actual justification for assigning a human owner to every
AI-assisted decision with real stakes, rather than a compliance formality:
it reflects where responsibility can mechanistically even live.

## Exercise

Find your own organization's actual AI-use policy (or confirm there
isn't one). Check it against the five questions in the table above.
For any question it doesn't answer, write the one sentence you think
the policy should say — and note who would need to approve that
sentence becoming official.
