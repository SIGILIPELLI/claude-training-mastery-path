# 08 · Building Repeatable AI-Assisted Processes

A one-off good prompt is useful once. A repeatable process — one you or
your team can run the same way every time and trust the result — is
what actually compounds. This module covers turning ad hoc AI use into
a documented, reliable process.

## Why "I know how to do this" isn't enough

If a task depends on you remembering the right prompt structure, the
right context to include, and the right verification steps, it only
works when you personally do it, attentively, every time. A repeatable
process externalizes that knowledge so quality doesn't depend on one
person's memory on a given day — including your own on a day you're
tired or rushed.

## The anatomy of a documented AI process

A process worth documenting has five parts:

1. **Trigger** — when this process applies (e.g., "drafting a weekly
   status update," "summarizing a customer call transcript").
2. **Required inputs** — what context must be gathered and in what
   form before starting (Level 1's context-gathering habits, formalized).
3. **The prompt/persona** — the tested prompt or persona template
   (Level 2, Module 8), with placeholders for the variable parts.
4. **Verification step** — what specifically must be checked before
   the output is used (Level 2, Module 6), stated concretely rather
   than as "review it."
5. **Owner** — who maintains this process when it stops working or the
   underlying task changes.

Skipping the verification step or the owner is the most common failure
— a process without a verification step just automates the risk of
being wrong faster, and a process without an owner silently rots.

## From ad hoc to repeatable: an example

Ad hoc: "I usually paste the meeting notes into Claude and ask for a
summary, tweaking the prompt a bit each time."

Repeatable version:

- Trigger: after any external-facing client meeting.
- Inputs: raw notes plus the meeting's stated agenda.
- Prompt: a fixed template asking for decisions made, action items with
  owners, and open questions — tested against three past meetings to
  confirm it reliably surfaces action items.
- Verification: the meeting's assigned notetaker confirms action item
  owners are correct before the summary is sent.
- Owner: the notetaker role, documented in the team's meeting process
  doc.

The difference isn't the AI use — it's that the second version doesn't
depend on the same person's memory to work correctly every time.

## Where to draw the line on documenting

Not every task needs this treatment — a one-off exploratory question
doesn't need a process doc. Document a process when at least two of
these are true: multiple people do the task, it happens regularly
(weekly or more), a mistake would be costly or embarrassing, or you've
personally redone the same prompt-engineering work more than twice.

## Maintaining processes over time

A documented process is a snapshot, not a permanent artifact. Revisit
it when: the underlying task changes, the model or tool you're using
changes meaningfully, or the verification step catches a new kind of
failure it wasn't designed for. Build a light habit of a quarterly
glance at your most-used processes rather than waiting for a failure to
force the update.

## Exercise

Pick one AI-assisted task you currently do ad hoc and repeat at least
weekly. Write it up using the five-part structure above. Run it exactly
as documented for the next occurrence and note any place the
documentation didn't match what you actually needed to do — that gap is
the first thing to fix.
