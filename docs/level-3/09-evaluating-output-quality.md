# 09 · Evaluating AI Output Quality Systematically

"Does this look right?" is a weak evaluation method — it catches
obviously broken output but misses plausible-sounding errors, which are
exactly the errors AI assistants are most likely to produce. This
module covers evaluating output more systematically, building on the
verification habits from Level 1 and Level 2.

## Why "looks right" isn't a check

Fluent, confident, well-formatted output is not the same as correct
output — AI-generated text is optimized to read well regardless of
whether the underlying claims are true. A skim-level "looks right"
check filters for surface plausibility, which is precisely the quality
a wrong answer is most likely to have. Systematic evaluation requires
checking against something other than your own impression of the text.

## Dimensions of quality to check separately

Bundling "is this good" into one judgment hides which dimension
actually failed. Separate it into:

| Dimension | Question | How to check |
|---|---|---|
| Factual accuracy | Are the specific claims true? | Verify against a source, not against fluency |
| Completeness | Did it address everything asked? | Re-read the original ask line by line against the output |
| Relevance | Is everything in the output actually useful, or is some of it filler? | Cut anything that doesn't serve the stated goal |
| Internal consistency | Do the parts agree with each other? | Check numbers/claims that appear more than once |
| Fit for the audience/purpose | Is the tone and depth right for who'll read it? | Compare against a known-good example for that audience |

A response can score well on four of these and still be unusable
because of the fifth — a fluent, complete, internally consistent
summary built on one fabricated statistic is still wrong.

## Building a lightweight rubric

For a task you do repeatedly, write a short rubric once rather than
re-judging from scratch every time. Three to five criteria, each with a
concrete pass/fail bar, is usually enough:

- Every number is traceable to a source in the input.
- No claim appears in the output that wasn't in the input or explicitly
  marked as the model's inference.
- Action items name a specific owner.
- Length matches the stated constraint.

A rubric turns evaluation from a vague impression into a checklist,
which is both faster and more consistent across different reviewers.

## Spot-checking vs. full verification

Full verification of everything is often not practical at scale. A
reasonable middle ground: fully verify anything that's a specific,
checkable factual claim (numbers, quotes, named sources), and spot-
check the rest — pick a few claims at random rather than always
checking the first one, since errors aren't evenly distributed and a
person skimming will unconsciously check the same spot every time.

## Comparing outputs across attempts

When iterating a prompt (Level 3, Module 3), evaluate outputs against
each other on the same rubric rather than against a vague sense of
improvement — this is what turns iteration into an actual comparison
instead of a series of impressions that are hard to remember and
compare a week later.

## How It Actually Works

"Looks right" fails as a check for a specific, mechanistic reason covered
throughout this course but worth stating precisely here: fluency and
correctness are produced by the same process but are not the same
property, and a skim only samples the one that's easier to fake.

**Fluency is directly optimized for; factual correctness is only
indirectly and imperfectly correlated with it.** Training rewards outputs
that read as coherent, well-structured, and confident — those are the
surface features a skim-level read actually evaluates. Whether a specific
claim, number, or citation inside that fluent text is true depends on
whether the model had (and correctly used) grounded information, which is
an entirely separate question a skim cannot answer, because a wrong claim
and a right one can be equally well-written.

**Checking dimensions of quality separately works because different
dimensions depend on different parts of the mechanism.** Factual accuracy
depends on whether real, grounded information was in context (Module 6,
Level 2); internal consistency depends on whether the generation
maintained coherent conditioning across a long response without drifting;
completeness depends on whether every part of your instruction actually
got attended to and addressed, since a long, multi-part prompt can have a
sub-request under-weighted relative to others. Splitting these into
separate checks matters because a single "does this look good overall"
judgment blends signals that have genuinely different failure
mechanisms — an output can score well on one and poorly on another
simultaneously.

**Comparing outputs across multiple attempts is a direct, practical way to
observe sampling variance.** Because generation samples from a probability
distribution rather than computing one deterministic answer, running the
same prompt more than once and comparing results shows you where the
distribution is peaked and confident (attempts agree) versus wide and
uncertain (attempts diverge) — which is a genuine, checkable signal about
reliability that a single output can never reveal on its own.

## Exercise

Take a recent piece of AI-assisted output you used without a formal
check. Apply the five-dimension breakdown to it after the fact.
Identify which dimension, if any, you skipped at the time — and write
one rubric line that would have caught it, for use on the next similar
task.
