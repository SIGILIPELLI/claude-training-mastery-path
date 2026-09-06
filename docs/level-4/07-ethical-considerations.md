# 07 · Ethical Considerations in AI-Assisted Work

Governance (Module 3) covers what an organization requires. Ethics
covers what's right even where nothing requires it — the situations
where the policy is silent or ambiguous and the decision comes down to
individual judgment. This module works through the recurring ethical
questions that come up in AI-assisted work.

## Disclosure: when to say AI was involved

There's no single universal rule, but a useful test is: would the
recipient's assessment of the work change if they knew AI drafted or
assisted it? If yes, disclosure is the honest default — for a
performance review, an academic submission, a piece of journalism, or
anything presented as someone's independent judgment, silence
misrepresents the work. For a routine internal email or a first-draft
outline you substantially reworked, disclosure is usually unnecessary
because it wouldn't change anything meaningful about how the work is
assessed. When genuinely unsure, disclose — the cost of over-disclosing
is small; the cost of a discovered non-disclosure is trust, which is
expensive to rebuild.

## Attribution and originality

AI-assisted output that closely reproduces a specific source (Level 2,
Module 3's "verify anything specific" applies here too) raises the same
attribution questions as any other unattributed source use. Passing off
AI-assisted analysis as entirely your own original thinking, in a
context where originality is explicitly the point (a thesis, a
competitive proposal, an award submission), is a form of
misrepresentation regardless of whether any policy explicitly bans it.

## Fairness and bias in AI-assisted decisions

AI output reflects patterns in its training data, which can encode
biases the user doesn't intend and may not notice. This matters most
where AI assistance touches decisions about people — screening resumes,
drafting performance language, summarizing feedback about someone.
Treat any AI-assisted output that evaluates or characterizes a person as
needing the highest level of human review, not the lowest, precisely
because the failure mode (a subtly unfair characterization that reads as
reasonable) is exactly the kind of error fluent AI output is prone to
producing and humans are prone to missing.

## Impact on others' work and livelihoods

Introducing AI assistance into a workflow can shift who does what work
and how it's valued — this is not automatically wrong, but it's an
ethical question, not just an efficiency one, when it affects real
people's roles. Being honest about this impact, including with the
people affected, is part of the change-management responsibility from
Module 2, not separate from it.

## A simple test for ambiguous cases

When a situation isn't clearly covered by policy: would you be
comfortable if the person affected knew exactly how the output was
produced and reviewed? If the honest answer is "I'd rather they didn't
know," that discomfort is usually pointing at the actual ethical issue,
even if you can't immediately name it.

## How It Actually Works

The bias risk described above isn't a bug that a "less biased" model
release fixes outright — it's a structural consequence of how these
systems are trained. A language model learns to continue text by finding
statistical patterns across an enormous training corpus, and that corpus
is a snapshot of existing human writing, with all its existing skew: who
gets described with which adjectives, whose credentials get mentioned
and whose don't, which names cluster with which outcomes in historical
text. The model doesn't "believe" any of this — it has no beliefs — but
it reproduces the correlations it was shown, and those correlations tend
to surface most exactly where they matter most: in output that
characterizes a person. This is why "the model didn't intend to be
unfair" is true and irrelevant at the same time; intent isn't the
mechanism, pattern-matching against biased training data is, and no
amount of the model "trying harder" changes what patterns it learned.

This also explains why human review is the actual mitigation rather than
a better prompt. A biased pattern in the output is invisible from
inside a single generation — the model can't flag its own blind spot,
because a blind spot is precisely the thing it has no signal for. A
prompt that says "be fair and unbiased" changes surface phrasing (softer
words, more hedges) far more reliably than it changes the underlying
judgment, because the instruction is itself just more text the model
continues from, not a constraint on the statistical process underneath.
Catching a subtly unfair characterization requires a reader who brings
context the model doesn't have and doesn't need to have to sound
fluent — which is exactly why fluency is the trap: confident, well-formed
sentences read as considered judgment even when the underlying signal is
just "this pattern was common in the training data," and the more fluent
the output, the harder people find it to apply the same scrutiny they'd
apply to a rougher first draft.

The disclosure question has a similar structural root. Nothing in how
these models generate text distinguishes "this is a first-draft outline
I'll heavily rework" from "this is a finished, publishable assessment of
a person" — the model produces both with the same fluent confidence,
because fluency is a property of the generation process, not a signal
about how much downstream verification the content has or needs. That
asymmetry — output confidence is constant, but appropriate trust varies
enormously by context — is exactly why the "would their assessment
change" test in this module has to live outside the model, as a judgment
call only the human in the loop can make.

## Exercise

Think of one AI-assisted piece of work you've produced where disclosure
was genuinely ambiguous. Apply the "would their assessment change" test
to it in hindsight, and decide what you'd do differently, if anything,
next time a similar case comes up.
