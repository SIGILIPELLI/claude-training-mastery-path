# 03 · Using Claude for Long Documents & Summarization Strategies

Long inputs — reports, transcripts, contracts, codebases — need a different
approach than short prompts. This module covers how to summarize
effectively at length, and how to work around context limits when a
document is too large to paste in one go.

## Match the summary to the decision it supports

The most common summarization mistake is asking for "a summary" without
specifying what it's for. A summary for a busy executive, a summary for
someone about to negotiate a contract, and a summary for a teammate who
will implement a spec are three different documents from the same source.

| Purpose | What to ask for |
|---|---|
| Skim before a meeting | "3-5 bullets: what changed, what decision is needed, what's the deadline" |
| Due diligence on a contract | "Every clause that creates an obligation, a penalty, or an auto-renewal — quote the exact clause and page/section" |
| Implementing a spec | "A checklist of every requirement stated as a testable condition, grouped by feature area" |
| Catching up after missing a discussion | "Chronological: what was proposed, what objections came up, what was decided, what's still open" |

Always name the audience and the use — "summarize for a PM deciding
whether to greenlight this" beats "summarize this."

## Preserving what matters, discarding what doesn't

Ask explicitly for what to keep and what to drop, especially with
transcripts and meeting notes that mix substance with filler.

> "Summarize this call transcript. Keep: decisions made, action items with
> owners, numbers/dates mentioned, and any disagreement that wasn't
> resolved. Drop: small talk, restated context everyone already knew,
> and filler like 'yeah, totally' exchanges."

## Structured extraction vs. narrative summary

For long documents you'll refer back to, a structured extraction is more
useful than prose because it's scannable and diffable.

> "Extract from this 40-page vendor contract into a table: Clause topic,
> Section #, What it requires of us, What it requires of them, Risk level
> (Low/Med/High) if this clause is unfavorable. One row per distinct
> obligation."

## Handling documents too long for one prompt

When a document exceeds what you can paste at once (or exceeds a
conversation's practical context), chunk it deliberately rather than
truncating blindly:

1. **Split on natural boundaries** — chapters, sections, numbered clauses —
   not arbitrary character counts, so you don't cut a requirement in half.
2. **Summarize each chunk with the same structured template**, so the
   partial outputs merge cleanly.
3. **Ask Claude to reconcile the partial summaries** into one final pass:
   "Below are five section-by-section extractions from the same contract.
   Merge them into one table, deduplicate overlapping items, and flag any
   contradiction between sections."
4. **Spot-check the merge** against the original for anything that landed
   at a chunk boundary — boundary content is where errors cluster.

## Iterative summarization for very long or ongoing material

For a document that keeps growing (an ongoing meeting log, a running
incident timeline), keep a running summary instead of resummarizing from
scratch each time:

> "Here is the running summary so far, and the new transcript segment
> since the last update. Update the summary: add new decisions/action
> items, mark any previous action item as done if it's mentioned as
> complete, and don't repeat unchanged sections."

This keeps each pass cheap and keeps the summary from silently drifting as
the source grows.

## Verifying a summary of a long document

Long-document summaries are exactly where fabrication is easiest to miss —
you're less likely to reread all 40 pages to check a claim. Spot-check by:

- Picking 2-3 specific claims in the summary and finding them in the
  source verbatim.
- Asking Claude directly: "For each bullet above, quote the exact sentence
  from the source it's based on." A bullet with no matching source text is
  a fabrication or an over-generalization.
- Checking numbers and dates especially closely — these are where subtle
  errors (off-by-one section numbers, transposed dates) are most damaging
  and least visually obvious.

## How It Actually Works

Working around context limits only makes sense once you know what the
limit actually is and why it exists.

**The context window is a hard token budget, not a soft guideline.** Every
model has a maximum number of tokens it can attend over in a single
request — inputs plus generated output combined. This isn't an arbitrary
product restriction; it reflects real computational cost, since
self-attention's cost grows with the *square* of sequence length (every
token potentially attends to every other token). That's a mechanistic
reason, not just a business one, for why "just make the window bigger"
isn't free, and why chunking strategies exist at all.

**Chunking works by trading complete-context attention for a
retrieve-then-summarize pipeline.** When a document doesn't fit in one
window, splitting it into pieces and summarizing each separately means each
chunk gets full, undiluted attention — but the model never sees the whole
document in one pass, so it cannot directly relate a detail in chunk 1 to a
detail in chunk 9 unless that relationship survives into the intermediate
summaries you feed forward. This is precisely why iterative/rolling
summarization (carrying forward a running summary alongside each new
chunk) preserves cross-document connections better than summarizing chunks
in total isolation — the running summary is how continuity gets
re-injected into context.

**Even within one window, attention doesn't weight every token equally,
which is why structure and explicit purpose help.** As covered in Module 7
(Level 1), very long single-pass inputs can show uneven effective recall
across the input. Telling Claude *what the summary is for* before the
document gives the attention mechanism, in effect, a query to look for
matches against — the model is now attending to the document with a
specific target in mind, rather than trying to compress everything with
equal weight, which is closer to how targeted search differs from generic
compression.

**Verifying a long-document summary matters more, not less, precisely
because chunked or lossy-attention processing raises the odds that some
detail from the middle of the source got underweighted or dropped** —
independent of whether the content was true or false, it may simply not
have been strongly attended to at all when the summary tokens were
generated.

## Exercise

Take a document at least several pages long (a real report, a long email
thread, a policy document). Write a purpose-specific summarization prompt
naming the audience and what to keep/drop. Then pick two claims from the
output and verify each against the source. Note whether both held up.
