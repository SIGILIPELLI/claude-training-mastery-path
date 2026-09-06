# 03 · Prompt Iteration & Systematic Testing of Prompts

For a prompt you'll reuse many times — a persona, a workflow step, a
template — treating it as something you test and iterate on, rather than
something you write once and trust, produces much more reliable results.
This module covers how to do that systematically.

## Why "it worked once" isn't enough

A prompt that produces a great result on the example you happened to test
can still fail on the range of real inputs it will actually see. The
failure mode is specific: you tune a prompt against one input, it looks
perfect, and you don't discover it breaks on a different but equally
common input until it's already in use.

## Building a small test set

Before trusting a recurring prompt, assemble 4-6 representative inputs
that span the real range you expect:

- A typical, easy case
- An edge case (empty, unusually short, unusually long)
- A messy/ambiguous real-world case (contradictory info, missing fields)
- A case that's superficially similar to the typical case but should
  actually be handled differently

Testing against only easy cases is the single most common reason a prompt
"works in testing" and then fails in real use.

## Defining what "pass" means before you test

For each test input, write down what a correct output looks like *before*
running the prompt — otherwise it's easy to unconsciously grade a
plausible-looking output as a pass. For structured output, this can be
literal (exact columns, exact values); for open-ended output, it can be a
short checklist (tone right? length right? nothing fabricated? handled the
edge case explicitly rather than ignoring it?).

## Iterating on a failure

When a test case fails, change one thing at a time and re-test — changing
several things at once makes it unclear which change actually fixed (or
broke) something.

**Example iteration log:**

| Version | Change | Result on edge case |
|---|---|---|
| v1 | Original prompt | Silently skipped the empty-field case instead of flagging it |
| v2 | Added: "if a field is missing, write 'Not provided', don't skip the row" | Fixed the empty-field case, but broke formatting on the long-input case |
| v3 | Added an explicit column-count contract | Both cases pass |

Keeping this kind of short log (even informally) makes it much easier to
know why the current version is worded the way it is, instead of
rediscovering the same failure six months later.

## Regression-testing after a change

Once a prompt is working across your test set, re-run the *entire* set
after any future edit — not just the case that motivated the edit. It's
common for a fix targeted at one case to quietly regress a case that was
previously fine.

## Testing for consistency, not just correctness

For prompts used at any real volume, also check consistency: run the same
input twice and compare. Some variation is expected and fine; a
structural difference (different columns, a completely different
approach to the same request) signals the prompt is under-constrained
somewhere, even if both outputs are individually reasonable.

## When to stop iterating

A prompt doesn't need to be perfect — it needs to reliably clear the bar
for its actual use. Diminishing returns set in once it's handling your
real test set correctly and consistently; further polishing against
increasingly exotic edge cases is often not worth the time unless those
cases genuinely occur.

## How It Actually Works

Systematic prompt testing exists because of a fact about the underlying
mechanism that's easy to forget once a prompt "just works": generation is
sampled from a distribution, and prompts interact with input content in
ways that aren't fully predictable from one example.

**A single successful run is one sample, not proof of reliability.** Because
each token is drawn from a probability distribution rather than computed
deterministically, the same prompt can yield somewhat different output
across runs, and — more importantly for testing — the *same prompt template*
filled with a different but equally realistic input can land in a very
different region of that distribution. Testing against a small but varied
set of real inputs is the direct fix for this: it samples the actual space
of situations the prompt will face, rather than trusting the one draw you
happened to look at.

**Defining "pass" before testing matters because otherwise you're grading
against a moving, intuition-based bar.** A vague sense of "did this look
good" is itself an unreliable judgment — much like an unstructured
prompt (Module 2, Level 1), an unstructured evaluation criterion invites
inconsistent verdicts across test cases. Writing down explicit pass
conditions turns evaluation into something you can apply the same way
every time, independent of how a particular output happened to read in
the moment.

**Regression testing after a change is necessary because prompts are not
modular in the way code is.** Changing one instruction in a prompt changes
the token sequence the model conditions on for *everything* in the
response, not just the part related to that instruction — there's no
guarantee that fixing behavior on the case that prompted the edit didn't
shift behavior on a previously-passing case, because both are governed by
the same holistic conditioning, not independent code paths.

**Testing for consistency (not just correctness on one run) matters
because sampling variance is a real property of generation, not a
testing artifact** — for tasks where you need the same input to reliably
produce the same kind of output (a classification task, a structured
extraction), running the same test case multiple times and checking
agreement is the only way to see whether the prompt has actually narrowed
the distribution to one dominant answer, or merely got lucky once.

## Exercise

Take a prompt you use repeatedly. Build a 5-case test set following the
categories above (typical, edge, messy, similar-but-different, plus one
more of your choice). Run the current version against all 5, note
failures, and iterate one change at a time until all 5 pass — keeping a
short log of what you changed and why.
