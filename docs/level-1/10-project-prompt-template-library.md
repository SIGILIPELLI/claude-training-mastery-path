# 10 · Project — Build a Personal Prompt Template Library

This project pulls together everything from Level 1 into one lasting
deliverable: a personal library of reusable prompt templates for tasks you
actually do regularly. Instead of re-inventing a well-specified prompt every
time, you'll have a small set of proven starting points you can drop your
specifics into.

## Why a template library is worth building

You've now practiced writing prompts with clarity, context, and specificity
(Module 2), structuring conversations (Module 3), applying this to writing,
analysis, and code-adjacent tasks (Modules 4-6), supplying documents
(Module 7), iterating toward a good result (Module 8), and verifying output
(Module 9). A template library turns that one-off practice into a
repeatable asset — the next time you need to draft a status update or
review a document, you start from something that already works instead of
from a blank page.

## What makes a good template

| Property | Why it matters |
|---|---|
| **Placeholders for the variable parts** | So you can reuse the structure with new specifics each time (e.g., `[AUDIENCE]`, `[TOPIC]`, `[LENGTH]`) |
| **The fixed parts stay fixed** | Tone, format, and structure that worked well shouldn't be re-derived every time |
| **A note on what to verify** | If the task type tends to produce claims worth checking (Module 9), the template should remind you |
| **Scoped to a real, recurring task** | A template for something you do once isn't worth building — save it for things you'll reuse |

**Template pattern:**

> [Task instruction with fixed structure/tone] for [PLACEHOLDER: audience].
> [PLACEHOLDER: specific content or topic]. Format: [fixed format
> requirement]. Length: [PLACEHOLDER or fixed limit].
> *(Verify: [note anything this task type tends to need fact-checked])*

## Worked example: three templates built from this pattern

**Template 1 — Status update draft**
> "Turn these raw notes into a status update for [PLACEHOLDER: audience,
> e.g. 'my manager' or 'the whole team']. Structure: What's done / What's
> next / Blockers, each section max 2 bullets. Tone: direct, no hedging
> language. Notes: [PLACEHOLDER: paste raw notes]."
> *(Verify: any specific dates or numbers pulled from the notes match the
> source.)*

**Template 2 — Document review**
> "Review this [PLACEHOLDER: document type, e.g. 'contract clause' /
> 'onboarding doc' / 'proposal'] and flag: (1) anything unclear to a
> first-time reader, (2) anything inconsistent with [PLACEHOLDER: the
> standard/goal it should match]. List findings as bullets, most important
> first. Document: [PLACEHOLDER: paste document]."
> *(Verify: any claim the review makes about what's "standard" or
> "typical" — that's an opinion to check against a real reference, not a
> fact.)*

**Template 3 — Decision comparison**
> "Compare [PLACEHOLDER: option A] and [PLACEHOLDER: option B] on these
> criteria: [PLACEHOLDER: list 2-4 criteria that matter for this decision].
> Present as a table. Walk through the reasoning for each criterion before
> giving a one-sentence recommendation for [PLACEHOLDER: your specific
> situation/constraints]."
> *(Verify: any factual claims about the options themselves — pricing,
> features, capabilities — against their current official sources.)*

## Building your own library

1. **List 5-10 tasks you do repeatedly** that involve Claude (or could).
   Draw on the three tasks from Module 1's exercise plus anything else that
   comes up often — status updates, meeting recaps, first-draft emails,
   document reviews, brainstorming lists, comparison tables, code
   explanations.
2. **For each, write a template** following the pattern above: fixed
   structure/tone, placeholders for what changes each time, and a verify
   note where relevant.
3. **Test each template** with a real, current example — fill in the
   placeholders with something real and run it (if you have access to
   Claude). Revise the template based on what you get back, using the
   iteration skills from Module 8.
4. **Save the finished set somewhere you'll actually reuse it** — a note,
   a doc, a small file — organized by task type.

## Cheat sheet: template library checklist

| Check | Question |
|---|---|
| ✅ Recurring | Is this a task I'll genuinely do again, not a one-off? |
| ✅ Placeholders | Are the variable parts clearly marked? |
| ✅ Fixed structure | Does the template lock in the format/tone that already worked? |
| ✅ Verify note | Does it flag what kind of claim in the output deserves a fact-check? |
| ✅ Tested | Have I run it with a real example, not just written it in theory? |

## Exercise (the project deliverable)

Produce your personal prompt template library: **5 to 10 templates**, each
following the pattern above (fixed instruction + placeholders + verify
note), covering tasks you actually expect to reuse. Test at least 3 of them
with real content. This library is the concrete artifact that closes out
Level 1 — carry it forward into Level 2, where you'll extend it with more
advanced prompting techniques like few-shot examples and role framing.
