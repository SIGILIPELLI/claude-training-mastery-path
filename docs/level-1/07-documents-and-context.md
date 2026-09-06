# 07 · Giving Claude Documents & Context

So far this course has focused on what you type. But much of the real value
of Claude comes from giving it something to work *with* — a document, a
transcript, a spreadsheet excerpt, a set of notes. This module covers how to
supply that material effectively, and the basics of how "long context" (
handling a lot of supplied text at once) works and where its limits are.

Specific upload mechanisms and exact size limits vary by which Claude
product or interface you're using and change over time — check the current
documentation for the specifics of your setup. The concepts below are
durable regardless of the exact interface.

## Why supplying material beats describing it

Describing a document from memory ("it's about our Q3 numbers, revenue was
up but costs were also up...") loses detail and introduces your own
summarization bias before Claude even starts. Providing the actual document
lets Claude work from the real content.

| Weaker approach | Stronger approach |
|---|---|
| "Our contract has a clause about termination, something like 30 days notice — is that normal?" | *(paste or upload the actual contract, or the relevant clause)* "Is this termination clause standard, and what's unusual about it if anything?" |
| "I have a spreadsheet of customer complaints, mostly about shipping I think — what should we do?" | *(paste the actual complaint data or a representative sample)* "Categorize these complaints and tell me the most common theme." |

## How to frame a request around supplied material

Once you've given Claude something to work with, be specific about what you
want done with it — the same clarity/context/specificity principles from
Module 2 apply, now pointed at the supplied material.

| Weak framing | Strong framing |
|---|---|
| "Here's a document, what do you think?" | "Here's our current onboarding doc. Identify the 3 steps most likely to confuse a first-time user, and say why." |
| "Look at this data." | "Here's last month's expense data. Flag any single expense over $1,000 and any category that grew more than 20% versus the prior month." |
| "Read this and tell me about it." | "Read this transcript and list every commitment either party made, with who made it and by when." |

## Working with long documents

When you give Claude a long document, keep a few things in mind:

| Consideration | What to do about it |
|---|---|
| Very long material may need to be broken into sections | For a long document, consider asking Claude to summarize or process it section by section rather than all at once, especially if you notice quality dropping on later parts |
| Claude works from what's provided, not assumptions | If a document is incomplete or a section was cut off, say so — otherwise Claude may fill gaps with plausible-sounding assumptions |
| Position and relevance still matter | If there's one part of a long document that matters most, point to it explicitly ("focus especially on section 3") rather than assuming it'll be weighted correctly on its own |

## Multiple documents at once

For tasks that require comparing across sources — two contract drafts, a
transcript against a policy document — be explicit about which document is
which and what the comparison is for.

**Worked example:**

> "I'm giving you two versions of the same proposal — Draft A and Draft B.
> Compare them and tell me: (1) what's substantively different, not just
> reworded, and (2) which draft better addresses the client's stated concern
> about timeline risk."

Being explicit about labels ("Draft A," "Draft B") and the specific
dimension of comparison avoids a generic "here are some differences" answer.

## Cheat sheet: working with supplied material

| Situation | What to do |
|---|---|
| You have the actual document | Supply it directly rather than summarizing it from memory |
| The document is long | Consider breaking it into sections, especially if quality seems to drop later in it |
| The document is incomplete | Say so explicitly, so Claude doesn't paper over the gap |
| Multiple documents | Label each clearly and state the specific comparison you want |
| One part matters most | Point to it explicitly rather than assuming it'll stand out on its own |

## How It Actually Works

"Long context" isn't a separate feature bolted onto the model — it's the
same context window from Module 1, just with more of it occupied by
supplied material instead of conversation.

**A document you paste in becomes tokens sitting in context, exactly like
your instructions do.** There's no distinct "document memory" separate from
the conversation — the model sees one continuous sequence of tokens, and
the document's content is simply part of what attention can draw on when
generating a response. This is precisely why providing the actual document
beats describing it: your description is a lossy, second-hand summary
competing for the same context budget as everything else, while the real
document gives the model direct access to the original wording, numbers,
and structure to attend to.

**Attention has to spread across everything in the window, so position and
volume both matter.** A model's ability to relate a detail near the start
of a huge document to something near the end depends on attention
successfully linking distant tokens — and in practice, very long inputs can
show uneven "recall," where content in the middle of an enormous document
gets less effective attention than content near the beginning or end. This
is a real, mechanistic effect (not just a documentation caveat), and it's
why asking for something specific from a long document ("what does section
4 say about refund timelines") that narrows down what needs strong
attention tends to be more reliable than an open-ended "summarize this" on
a very long input.

**Multiple documents at once are just more tokens in the same window,
concatenated.** The model doesn't inherently know where one document ends
and another begins unless you (or the interface) mark that boundary clearly
— which is why labeling documents explicitly ("Document A: contract,
Document B: email thread") measurably helps: it gives the attention
mechanism a clean token-level signal for keeping the sources distinct
instead of blending them.

## Exercise

Take a real document you have on hand (an email thread, a policy doc, a set
of notes) and write two prompts: one asking Claude to extract something
specific from it (a list of action items, a set of dates, a summary focused
on one theme), and one asking it to evaluate the document against a
specific criterion you name. Be explicit in both about exactly what you want
done with the material, not just "look at this."
