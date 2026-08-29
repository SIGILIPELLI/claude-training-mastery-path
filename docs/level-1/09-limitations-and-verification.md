# 09 · Understanding Limitations & Verifying Outputs

Every module so far has built toward using Claude effectively. This one is
about the other half of the skill: knowing when to trust an output as-is,
when to verify it, and when not to rely on it at all. This is arguably the
most important module in this level — the habits here are what separate
someone who uses AI well from someone who gets burned by it once and stops
trusting it entirely, or worse, never notices the burn.

## Why AI systems can state incorrect things confidently

As covered in Module 1, Claude generates the most plausible-sounding
continuation of text, based on patterns learned from training data — it
does not have a built-in mechanism that guarantees every factual claim it
makes is true. This can produce **hallucinations**: confident, fluent,
plausible-sounding statements that are wrong — a fabricated statistic, a
citation that doesn't exist, a confidently stated "fact" that isn't one.
The dangerous part isn't that it's sometimes wrong — every source of
information sometimes is — it's that a wrong answer from Claude can look
exactly as polished and confident as a right one, with no visible tell.

## A simple risk framework

Not every task needs the same level of scrutiny. A useful way to triage:

| Risk factor | Low risk | High risk |
|---|---|---|
| **Stakes** | A draft you'll personally review before it matters | Something that gets sent, published, or acted on directly |
| **Verifiability** | You already know the right answer or can spot an error easily | You have no independent way to check it |
| **Specificity of the claim** | General guidance, structure, phrasing | Specific numbers, dates, names, citations, quotes |
| **Time sensitivity** | Timeless or slow-changing information | Recent events, current prices, current versions of anything |

The riskier a task scores across these factors, the more verification effort
it deserves before you act on the output.

## What to specifically verify

| Type of claim | How to verify |
|---|---|
| Statistics or figures | Check against the original source, your own data, or a trusted reference — don't assume a number is real just because it's stated precisely |
| Citations, quotes, or sources | Confirm the source actually exists and says what it's claimed to say — fabricated citations can look completely realistic |
| Names, dates, specific facts | Cross-check against a reliable source, especially for anything recent |
| "As of [time period]" claims | Treat cautiously — Claude's training data has a cutoff, and even within it, recency isn't guaranteed to be accurate |
| Claims about Claude/Anthropic itself (models, pricing, features) | Check the current [Claude documentation](https://docs.claude.com/) — these change over time and even Claude may not have perfectly current information about itself |

## Techniques that help (but don't replace verification)

| Technique | What it does | What it doesn't do |
|---|---|---|
| Ask Claude to flag its own uncertainty ("tell me if you're not confident about any of this") | Often surfaces some genuine uncertainty | Doesn't guarantee every wrong claim gets flagged — a model can be confidently wrong without "knowing" it |
| Ask for reasoning, not just conclusions (Module 5) | Gives you visible logic to sanity-check | The reasoning itself can also contain a wrong assumption |
| Ask it to cite where a specific claim came from | Can help you locate what to verify | If no real source is given or a citation is fabricated, this doesn't help — verify the citation itself |
| Cross-check with a second source or a fresh conversation | Independent-ish check | Two guesses can still agree and both be wrong, especially on obscure topics |

None of these techniques are a substitute for actually checking anything
that matters — they reduce risk, they don't eliminate it.

## A worked example of the risk framework in action

**Task:** drafting a blog post that mentions "in 2019, X% of small
businesses adopted cloud accounting software."

- **Stakes:** medium — it's published content, but a wrong stat is
  embarrassing rather than dangerous.
- **Verifiability:** the specific percentage is a checkable fact.
- **Specificity:** high — an exact number and year, exactly the kind of
  claim most likely to be a fabricated-sounding-precise hallucination if
  not independently confirmed.
- **Time sensitivity:** it's historical, so it won't have changed, but that
  doesn't mean the number as stated is accurate.

**Conclusion:** this specific claim is a "verify before publishing" item —
look up the actual figure from a real source rather than trusting the
number as given, even though the rest of the post (structure, phrasing) can
be trusted as a normal first draft.

## Cheat sheet: when to double-check

| If the output contains... | Do this |
|---|---|
| A specific number, date, or statistic | Verify against a real source before using it |
| A quote or citation | Confirm the source exists and says that |
| A claim about very recent events | Treat as possibly outdated or unconfirmed |
| A claim about Claude/Anthropic specifics (models, pricing, limits) | Check current official documentation |
| General structure, phrasing, brainstormed ideas | Lower risk — normal first-draft trust level applies |
| Anything going out under your name with real stakes | Full read-through and fact-check before it ships, regardless of format |

## Exercise

Take an output from any earlier exercise in this course (or generate a new
one on a topic with a few factual claims in it — history, statistics,
current events). Go through it and label each specific factual claim as
Verify, Probably Fine, or Not Applicable, using the risk framework above.
For the "Verify" items, write down where you'd actually go to check them.
