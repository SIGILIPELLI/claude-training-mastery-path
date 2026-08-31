# 01 · Advanced Context Management for Long Projects

Working with Claude across a long-running project — weeks of iteration, a
large codebase, an evolving document — requires actively managing what
context Claude has, rather than relying on one long unstructured
conversation. This module covers the practical techniques.

## Why long conversations degrade

As a conversation grows, several things happen: earlier instructions can
get proportionally less weight relative to everything said since, the
model has more (sometimes contradictory) material to reconcile, and it
gets harder for *you* to remember what's already been established. A
conversation that's drifted or is producing inconsistent answers is often
better restarted with a tight recap than pushed further.

## Maintaining a living context document

For any project that spans multiple sessions, maintain a standalone
context document — separate from the conversation itself — that captures
the state Claude (and you) need going forward:

> **Project context: [name]**
> - Goal: [one sentence]
> - Key decisions so far: [bullet list, dated]
> - Current constraints: [budget, deadline, technical limits]
> - Terminology/conventions specific to this project: [glossary]
> - Open questions: [what's still undecided]

Paste this at the start of a new conversation instead of trying to
re-derive context from scratch or scrolling back through old threads. In
Claude Code, this document is exactly what a `CLAUDE.md` file is for — it's
read automatically at the start of every session.

## Chunking context deliberately

For large source material (a full codebase, a long document set), decide
up front what Claude actually needs for the current step rather than
providing everything by default:

- **Task-scoped context**: only the files/sections relevant to the current
  sub-task, not the entire project. This keeps responses focused and
  avoids the model reconciling irrelevant material.
- **Reference on demand**: mention that other context exists and can be
  provided if needed, rather than paginating everything in preemptively.
- **Summarized history**: for context that's mostly settled (early
  decisions that won't change), a compressed summary is more useful than
  the original raw discussion.

## Handling context that spans sessions

When you can't carry a live conversation forward (a new session, a new
day), a short recap message that restates only what's still relevant is
more reliable than assuming continuity:

> "Continuing the [project] work. Recap: we decided on [X], the current
> constraint is [Y], and the open question is [Z]. Today's task: [...]."

This is cheap and removes ambiguity about what state you're both actually
starting from.

## Managing conflicting or superseded context

Long projects accumulate decisions that get revised. If you paste an old
context document that includes a decision that's since changed, Claude
has no way to know it's stale unless you say so:

> "Note: the budget mentioned in the attached doc ($10k) is outdated — the
> real number is now $15k. Use $15k for everything below."

Flag superseded information explicitly rather than trusting it to be
overridden by something said later — silent contradictions are a common
source of subtly wrong output in long-running work.

## A context audit before a high-stakes step

Before a consequential deliverable (a client-facing document, a decision
that's hard to reverse), do a quick audit: re-read what context Claude
actually has versus what's in your head but never stated. It's common to
assume Claude "knows" something because you discussed it days ago in a
different conversation — if it's not in the current context, it isn't
actually available.

## Exercise

For a real multi-session project you're working on with Claude, write a
living context document using the template above. Use it to start your
next session instead of re-explaining background from memory, and note
whether it changed how much recap you needed to type.
