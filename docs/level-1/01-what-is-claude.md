# 01 · What Is Claude?

Claude is an AI assistant made by Anthropic that you talk to in natural
language — you type (or speak) what you want, and it responds with text
(and, in some contexts, other outputs like generated code or images it
describes). Before using any tool well, it helps to have an honest, durable
picture of what kind of thing it is, what categories of task it's actually
good for, and where the edges are. This module builds that picture. It
deliberately avoids naming specific model versions, exact pricing, or exact
feature availability — those change over time, so for anything precise,
check the [current Claude documentation](https://docs.claude.com/) rather
than trusting a snapshot from any single course, including this one.

This course is an independent educational resource. It is not produced,
endorsed, or reviewed by Anthropic.

## What kind of thing Claude is

Claude is a **large language model (LLM)** — a system trained on enormous
amounts of text to predict and generate language, then further trained to be
helpful, follow instructions, and avoid harmful or low-quality responses. A
few properties follow directly from that:

| Property | What it means in practice |
|---|---|
| It generates text one piece at a time | Responses are produced progressively, which is why longer answers "stream in" rather than appearing instantly |
| It has no persistent memory by default | Unless a product surface explicitly adds memory or you re-supply context, each new conversation starts fresh |
| It has a knowledge cutoff | Its training data ends at some point in time, so it may not know about very recent events unless given that information or given tools to look things up |
| It doesn't "know" it's right | It produces the most plausible-sounding continuation of the text so far, which usually means an accurate, well-reasoned answer — but not always (more in Module 9) |
| It can follow structure and instructions | You can ask it to write in a specific format, adopt a role, or follow a process, and it will generally comply |

None of this makes Claude less useful — it just means the tool works best
when you understand it as a very capable, very fast collaborator with a
particular kind of blind spot, not as a database or a search engine.

## What Claude is generally good at (durable capability categories)

Rather than listing specific features that may change, it's more useful to
think in categories of task. Across the products Claude ships in, it's
generally strong at:

| Category | What it looks like | Example ask |
|---|---|---|
| **Writing** | Drafting, editing, rewriting in a different tone, summarizing | "Draft a two-paragraph project update for a non-technical stakeholder" |
| **Analysis & reasoning** | Working through a problem step by step, comparing options, structuring an argument | "Compare these three vendor options against our stated priorities" |
| **Conversation** | Back-and-forth discussion, brainstorming, explaining a concept at your level | "Explain this contract clause like I've never seen one before" |
| **Code-adjacent work** | Explaining code, reviewing a snippet for issues, generating a first draft of a script | "What does this function do, and where could it fail?" |
| **Working with supplied material** | Summarizing or answering questions about a document, transcript, or dataset you provide | "Summarize the key risks in this report" |

The common thread: Claude is strongest when the task is about **transforming
or reasoning over language and structured thinking** — turning a rough idea
into a draft, turning a long document into a summary, turning a vague
problem into a structured comparison.

## What Claude is not

| It is not... | Because... |
|---|---|
| A search engine | It doesn't browse the live web by default in every context, and its training data has a cutoff — treat time-sensitive facts as something to verify, not assume |
| An oracle of certainty | It can state incorrect things confidently (see Module 9) — it's a collaborator to verify, not a final authority |
| A replacement for domain expertise | It can help you think through a legal, medical, or financial question, but it is not a substitute for a licensed professional's judgment |
| A fixed, unchanging product | Anthropic updates and releases new models and features over time — specific capabilities, limits, and pricing you read about elsewhere may be out of date by the time you read this |

## A simple mental model

A useful way to think about Claude: **it's a fast, well-read collaborator
who has never met you, doesn't remember yesterday unless you tell it, and
will confidently answer a question it doesn't actually know the answer to
unless you ask it to flag its own uncertainty.** Every technique in the rest
of this course is really just a way of working around, or working well
with, that one sentence.

## Cheat sheet: setting expectations before you start

| Question to ask yourself | Why it matters |
|---|---|
| Does this task need very recent information? | If yes, plan to verify or supply that information yourself — don't assume Claude has it |
| Does this task need real domain expertise with real stakes (legal, medical, financial)? | Use Claude to think through it, not as the final decision-maker |
| Does this task depend on something specific to me or my organization? | Claude won't know it unless you tell it — plan to supply context (Module 7) |
| Is this a "generate a draft" or "verify a fact" task? | Claude is much stronger at the former; treat the latter with more scrutiny (Module 9) |
| Am I starting a new conversation? | Remember it has no memory of prior conversations unless the product you're using explicitly provides that |

## How It Actually Works

Under the hood, "predicting text one piece at a time" is more specific than
it sounds, and understanding the mechanism explains most of Claude's
strengths and blind spots at once.

**Tokens, not words.** Claude doesn't read or write in whole words — it
operates on **tokens**, chunks of text (often a few characters, sometimes a
whole common word) produced by a fixed tokenizer. Your prompt is converted
into a sequence of token IDs, and the model's only job, repeated many times,
is: given the tokens so far, output a probability distribution over what
token comes next. It samples one token from that distribution, appends it,
and repeats — that's the "streaming" you see. This is also why Claude can
be worse at character-level tasks like counting letters in a word: it never
directly sees individual letters, only token chunks.

**The context window is the model's entire working memory.** Every token
you've sent — system instructions, your messages, its own prior replies in
the conversation — gets fed back in on every single generation step, because
the model has no memory that persists between calls on its own. It isn't
"remembering" the conversation the way you remember a chat from yesterday;
each response is generated from scratch by re-reading the entire visible
transcript up to a fixed token limit. This is precisely why a fresh
conversation starts with zero knowledge of previous ones: nothing was
carried over, because nothing is stored outside that one context window.

**Attention is what lets it use that context at all.** The mechanism that
lets a token attend to *any* earlier token — not just the ones right before
it — is called self-attention. For each token being generated, the model
computes a weighted relevance score against every token already in context,
which is how a reference on line 1 of a long prompt can still influence a
response generated at line 500. That relevance weighting is also why
*where* you place important instructions and *how much irrelevant material*
surrounds them measurably affects output quality — it's not superstition,
it's a direct consequence of attention having to spread its "budget" across
everything in context.

**Confidence is a byproduct of probability, not of truth-checking.** Because
the model is fundamentally choosing the statistically most plausible next
token given its training, a fluent, grammatically confident sentence and a
factually correct one are optimized for the same thing: plausibility of
form. There is no separate internal step that checks a claim against a
ground-truth database before it's produced (unless the product explicitly
adds a tool for that, like web search). This is the mechanistic reason
behind the "confidently wrong" behavior described above — it's not a bug in
an otherwise truth-checking process, it's the direct result of there being
no such process by default.

## Exercise

Write down three tasks from your own week — one writing task, one analysis
or research task, and one task involving a document or a decision. For each,
answer:

1. Which capability category above does it fall into?
2. Does it depend on very recent information, deep domain expertise with
   real stakes, or facts specific to you that Claude wouldn't already know?
3. Based on that, would you trust a first draft from Claude as-is, use it as
   a starting point to edit, or use it mainly to think out loud?

You'll use these three tasks again in later modules as you learn to prompt,
structure, and verify more effectively.
