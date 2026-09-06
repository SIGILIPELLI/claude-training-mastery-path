# 05 · Using Claude for Brainstorming & Ideation

Claude is useful for widening the option space before you narrow it —
generating more raw ideas, more angles, and more variations than you'd
produce alone in the same amount of time. This module covers how to
brainstorm productively rather than getting a list of the same five
obvious ideas restated.

## Ask for range, not just quantity

"Give me 20 ideas" often produces 20 minor variations on the first idea
that came to mind. Asking for range forces genuine spread.

> "Give me 12 name ideas for this product. Cover at least 4 different
> approaches: literal/descriptive, invented word, metaphor from an
> unrelated domain, and playful/pun-based. Label each idea with which
> approach it uses."

Labeling by approach does two things: it forces actual diversity (Claude
can't put 8 ideas under "literal" and call it done), and it lets you
quickly scan for the *type* of idea you're drawn to, not just individual
options.

## Constraints sharpen brainstorms

Unconstrained brainstorming tends toward generic ideas. Real constraints —
budget, audience, an ingredient that must be included, something explicitly
excluded — push toward more specific, more useful ones.

**Weak:** "Brainstorm marketing campaign ideas."

**Sharper:** "Brainstorm marketing campaign ideas for a $5,000 budget,
targeting first-time home buyers aged 28-35, that can launch within 3
weeks. Exclude anything requiring paid influencer partnerships — we don't
have those relationships yet."

## Building on ideas instead of discarding

Rather than treating a brainstorm as one-shot, treat it as a dialogue:
pick the 2-3 ideas with the most promise and ask Claude to develop them
further, combine them, or push a chosen idea past its obvious version.

> "Idea #4 (a referral program tied to a local charity) is the strongest.
> Give me 3 concrete variations of it — different mechanics for how the
> referral and donation connect — and for each, one likely reason it could
> fail."

Asking for a likely failure mode alongside each variation keeps the
brainstorm honest instead of only generating enthusiasm.

## Using constraints to break out of an obvious rut

If early ideas feel same-y, add an artificial constraint specifically to
force different thinking, then relax it afterward.

| Rut-breaking constraint | Effect |
|---|---|
| "Ideas that cost $0 to implement" | Forces creativity over budget-driven ideas |
| "Ideas assuming we can't use email or social media" | Surfaces channels you'd normally default past |
| "How would a completely different industry solve this?" | Imports patterns from outside your usual frame |
| "The oppposite of the obvious approach" | Surfaces contrarian options worth at least considering |

## Structuring a brainstorm session end-to-end

A repeatable pattern for a full session:

1. **Diverge widely** — ask for range across explicit categories (as above).
2. **Cluster** — "Group these 20 ideas into 4-5 themes and name each theme."
3. **Evaluate against real criteria** — "Score each theme 1-5 on Feasibility, Cost, and Expected Impact, with one sentence justifying each score."
4. **Converge** — "Given those scores, which 2 themes would you pursue first, and why?"

Doing this as separate prompts (rather than one giant ask) gives you a
natural place to redirect after each step if the direction isn't right.

## What brainstorming with Claude won't tell you

- **It doesn't know your market as well as you do.** Ideas need your
  judgment about what's actually feasible, on-brand, or already tried and
  failed — Claude has no memory of your last three attempts unless you
  tell it.
- **Popularity isn't validation.** An idea appearing plausible and
  well-articulated says nothing about whether it will actually work; use
  brainstorming to widen options, not to substitute for testing them.

## How It Actually Works

Why does "give me 20 ideas" tend to collapse into near-duplicates, while
"cover 4 different angles" doesn't? It comes down to sampling and how the
model avoids (or fails to avoid) repeating itself.

**Generation is sampled from a probability distribution, and the most
likely tokens dominate unless something pushes generation elsewhere.** At
each step, the model has a ranked distribution over next tokens; left
alone, a long list-generation task naturally gravitates toward the highest-
probability continuation pattern repeatedly, which tends to be a set of
closely related variations on whatever idea got the most reinforcement
first — because the earlier ideas in the list are now in context too,
biasing later ones toward similarity via attention.

**Explicit categories function as forced conditioning changes mid-
generation.** When you ask for ideas "across 4 different angles," you're
requiring the model to change what it's conditioning on for each block —
angle 1's ideas are generated with "angle 1" framing in context, angle 2's
with different framing — which pushes the distribution to genuinely
different regions of it rather than resampling near the same peak
repeatedly. This is a direct, mechanistic reason categorized brainstorm
prompts produce more genuine variety than a flat quantity request.

**Constraints work the same way pruning works in search: they eliminate
the most statistically common (and therefore least surprising) answers.**
A constraint like "under $500" or "no plugins" removes the highest-
probability generic ideas from being valid continuations, forcing the
model into less-traveled, lower-probability — and often more interesting —
regions of its learned distribution. This is the actual mechanism behind
"constraints breed creativity" here, not a motivational platitude.

**What brainstorming can't give you: genuinely novel-to-the-world ideas
outside its training distribution.** Every idea, however creatively
recombined, is still built from patterns present somewhere in training
data — the model doesn't have lived experience of your specific market or
users to draw an idea from that didn't already exist in some form in what
it learned from. That's the mechanistic reason validation and real-world
testing (not more brainstorming) is what actually separates a good idea
from a merely plausible-sounding one.

## Exercise

Pick a real problem you're brainstorming for (a name, a campaign, a
feature, a process fix). Run the four-step session above: diverge with
explicit categories, cluster into themes, score against your real
criteria, then converge. Note which theme you'd have missed if you'd just
asked for "some ideas" up front.
