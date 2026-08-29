# 03 · Structuring a Conversation

Most real work with Claude isn't a single prompt-and-response — it's a
conversation, where each message can build on, refine, or correct what came
before. This module covers how to use multi-turn context deliberately: how
follow-ups work, how to correct course without starting over, and how to
structure a longer working session so it stays productive.

## How multi-turn context works

Within a single conversation, Claude can see everything said so far (up to
the limits of its context window — the amount of text it can consider at
once). That means:

- You don't need to re-explain background you already gave earlier in the
  same conversation.
- You can refer back to something ("the second option you gave me," "the
  version before you shortened it").
- Corrections apply going forward — if you say "actually, make it shorter,"
  Claude uses that as new guidance for what follows, not just for that one
  message.

This is different from starting a **new** conversation, which begins with no
memory of anything said before (Module 1) — so if you want continuity,
you generally need to stay in the same thread.

## Follow-ups: build, don't restart

A common beginner mistake is re-writing a long, fully-specified prompt from
scratch every time you want a small change, when a short follow-up would do.

| Instead of restarting with... | Just say... |
|---|---|
| "Write a product description for our app, for small business owners, emphasizing ease of setup, but this time make it funnier." | "Make that funnier." |
| "Summarize this document in 3 bullets, but actually focus more on the budget numbers instead." | "Redo that, but focus more on the budget numbers." |
| "Compare these two vendors again but add a column for support quality." | "Add a column for support quality to that table." |

Short, targeted follow-ups are faster to write, and they let Claude use the
full context of what it already produced rather than starting from zero.

## Correcting course without losing the thread

If a conversation goes in the wrong direction, you don't need to abandon it
— name the problem specifically and redirect.

**Worked example:**

> **You:** Draft an email to a client explaining a two-week delay.
>
> **Claude:** *(drafts an apologetic, somewhat lengthy email)*
>
> **You:** This is too apologetic — we didn't cause the delay, a shipping
> partner did. Make it more matter-of-fact and half the length.
>
> **Claude:** *(revises accordingly)*
>
> **You:** Better. Now add one sentence offering a small goodwill discount.

Each turn is a small, specific correction — tone, length, then one addition
— rather than a fresh restart. This is both faster and tends to converge on
what you actually want more reliably than trying to specify everything
perfectly in the first message.

## Structuring a longer working session

For multi-step work (research, drafting a longer document, working through
a decision), it helps to signal structure explicitly rather than letting the
conversation wander.

| Technique | Example |
|---|---|
| **State the overall goal up front** | "Over this conversation I want to end up with a one-page project brief. Let's build it section by section." |
| **Work in stages** | "First, just help me list the sections we need. Don't write content yet." |
| **Checkpoint before moving on** | "That list looks right. Now draft the first section." |
| **Ask for a recap when a thread gets long** | "Summarize what we've decided so far before we continue." |
| **Explicitly close out a sub-topic** | "Good, that section is done. Let's move to the next one." |

This staged approach avoids a common failure mode: asking for the entire
finished deliverable in one giant prompt, getting something broadly right
but wrong in three places, and then struggling to fix all three without the
fix to one undoing another.

## When to start a new conversation instead

Not everything belongs in one long thread. Consider starting fresh when:

| Signal | Why |
|---|---|
| You're switching to a completely unrelated task | Irrelevant prior context can occasionally bias or clutter a new task |
| The conversation has gotten very long and unfocused | It gets harder for you (and sometimes for the quality of responses) to track what's been decided |
| You want a genuinely independent second opinion | Asking the same conversation thread tends to get an answer consistent with what it already said; a fresh conversation with the same prompt gives you a more independent take |

## Cheat sheet: conversation structure

| Situation | Move |
|---|---|
| Small tweak to the last output | Short, specific follow-up — don't restart the whole prompt |
| Output going the wrong direction | Name the specific problem, then redirect — don't just repeat the original ask |
| Big multi-part deliverable | Break into stages, checkpoint after each |
| Long thread getting confusing | Ask for a recap, or explicitly summarize decisions yourself |
| Need an independent take | Start a new conversation, not a follow-up in the same one |
| Switching topics entirely | Start a new conversation |

## Exercise

Pick a task that has at least two rounds of revision in it (e.g., drafting
something, then improving tone, then trimming length). Write out the
conversation as a script: your opening prompt, an imagined first response,
then two follow-up corrections you'd give — each one short and specific,
each building on the last rather than restarting. If you have access to
Claude, run it for real and compare how close your imagined responses were.
