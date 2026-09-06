# 04 · Using Claude for Writing Tasks

Writing is one of the categories Claude tends to be strongest at (Module 1)
— drafting from scratch, editing existing text, adjusting tone, and
summarizing. This module works through each of those sub-tasks with
concrete prompt patterns and before/after examples.

## Drafting from scratch

When drafting, the quality gap comes almost entirely from how much context
and specificity you provide (Module 2). A useful pattern: state the format,
audience, tone, length, and key points to include, then let Claude produce
a first draft to react to — not agonize over the perfect first prompt.

| Weak draft prompt | Stronger draft prompt |
|---|---|
| "Write a bio for me." | "Write a 3-sentence professional bio for a LinkedIn profile. I'm a freelance graphic designer, 6 years experience, specializing in brand identity for small businesses. Tone: confident but approachable, no buzzwords like 'passionate' or 'synergy'." |
| "Write a cover letter." | "Write a cover letter for a marketing coordinator role at a nonprofit. I have 2 years of social media experience and led a fundraising campaign that raised $15,000. Keep it under 250 words, and open with the fundraising result, not a generic intro." |

## Editing existing text

For editing, give Claude the actual text and say precisely what kind of edit
you want — copyedit, tone shift, trim, or restructure are different jobs.

| Edit type | Prompt pattern | Example |
|---|---|---|
| Copyedit | "Fix grammar and clarity only, don't change my voice or meaning." | Useful when the content is right but the prose is rough |
| Tone shift | "Rewrite this to sound [more formal / warmer / more direct], keeping the same content." | Useful when the content is right but doesn't fit the audience |
| Trim | "Cut this to under [X] words without losing the main point." | Useful for word/character limits |
| Restructure | "Reorder this so the conclusion comes first, then the supporting points." | Useful when the logic is right but the order isn't |

**Worked example — tone shift:**

> Original: "Hey team, so I wanted to just flag that we're probably going to
> be a bit behind on the Q3 report, sorry about that, just a lot going on
> this week, will try to get it done soon-ish."
>
> Prompt: "Rewrite this to sound more professional and confident, without
> being cold. Keep the core message: the Q3 report will be late, no firm new
> date yet."
>
> Result (what to expect): a version that states the delay plainly, drops
> the hedging language ("probably," "bit," "soon-ish"), and reads as an
> update rather than an apology — while keeping the same underlying facts.

## Summarizing

Summarization quality depends heavily on telling Claude what the summary is
*for* — a summary for yourself to skim later is different from one you're
handing to someone else to act on.

| Weak summarize prompt | Stronger summarize prompt |
|---|---|
| "Summarize this." | "Summarize this in 5 bullet points, focused only on action items and deadlines — I'm sending this to my manager." |
| "Summarize this article." | "Summarize this article in 2 sentences, as if explaining it to a friend who has no background in the topic." |
| "TL;DR this thread." | "Summarize this email thread into 3 bullets: what was decided, what's still open, and who owns the next step." |

## Worked example: taking a task end-to-end

**Scenario:** you have a messy 400-word paragraph of notes from a meeting
and need a clean update to send to stakeholders.

1. **Draft prompt:** "Turn these meeting notes into a clean, organized
   status update. Structure: What shipped this week, What's blocked, What's
   next. Keep it to one short paragraph per section." *(paste notes)*
2. **Review the draft** — check it against what actually happened; Claude
   may have inferred a connection between two notes that wasn't really
   there (see Module 9 on verification).
3. **Tone follow-up:** "Make the 'What's blocked' section a bit more direct
   — right now it reads like we're not sure it's actually blocked."
4. **Trim follow-up:** "Cut the whole thing to fit in one email screen,
   roughly 150 words total."

Each step is a small, specific instruction building on the last — the
pattern from Module 3 applied specifically to a writing task.

## Cheat sheet: writing task prompts

| Task | Key things to specify |
|---|---|
| Draft from scratch | Format, audience, tone, length, key points to include |
| Copyedit | "Don't change voice or meaning" (if that matters to you) |
| Tone shift | The target tone, and what to keep unchanged |
| Trim | Target length, what's most important to preserve |
| Restructure | The new order or structure you want |
| Summarize | Purpose of the summary, audience, format (bullets vs. prose), length |

## How It Actually Works

Drafting, editing, and summarizing feel like different skills to us, but
they're the same underlying mechanism — next-token prediction — applied
with different conditioning.

**Drafting from scratch is pure generation from a prompt's conditioning.**
When there's no existing text to work from, every token is chosen based
only on your instructions and the model's training. This is why specificity
matters so much more here than in editing: with nothing else to anchor to,
the model's only signal for "what should this sound like" is what you put
in the prompt, so an under-specified draft prompt tends to regress toward
the statistically most common way that kind of text gets written.

**Editing is generation conditioned on your original text as additional
context.** When you paste in existing text and ask for a rewrite, that text
sits in the context window as strong, specific conditioning — the model
attends heavily to your actual word choices, structure, and content, so the
output stays much closer to "your text, adjusted" than "a fresh generic
draft." This is why editing prompts are more forgiving of vagueness than
drafting prompts: the source text itself is already doing a lot of the
narrowing that Module 2 described, which is also why editing prompts that
*don't* clearly say what to change can accidentally leave the original
mostly untouched — there's nothing pulling the distribution away from just
reproducing what's already there.

**Summarizing is a compression task under the same token-by-token process.**
There's no separate "extract the key points" subroutine — the model
generates a shorter continuation conditioned on the full source text (as
much of it as fits in context), one token at a time, guided by your
instructions about length and focus. This is why summary quality degrades
gracefully rather than failing outright when a document is long: as long as
the material fits in the context window, attention can still draw on all of
it, but the more that's competing for attention, the more a summary prompt
benefits from stating exactly what to prioritize (Module 2's specificity
principle again).

## Exercise

Take a real piece of writing you have sitting around — an email, a set of
notes, an old draft — and do three things with it: (1) ask for a summary
aimed at a specific audience, (2) ask for a tone shift, and (3) ask for it
to be trimmed to half its length. Write out all three prompts, being
specific about audience, tone, and target length in each. Compare the three
outputs against what you expected.
