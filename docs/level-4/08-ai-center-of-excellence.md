# 08 · Building an AI Usage Center of Excellence

A center of excellence (CoE) is the structural answer to the problem
raised in Module 1: individual skill doesn't reliably become
organizational capability on its own. This module covers what a CoE
actually needs to do, at a scale appropriate to your organization — this
does not require a large formal team to start.

## What a CoE is actually for

A CoE's job is to be the place where good patterns get collected,
improved, and spread — instead of each team or person separately
reinventing the same template, the same review process, the same
answer to "is this data safe to paste in." Without something playing
this role, an organization stays permanently at the "ad hoc" stage from
Module 1's maturity curve regardless of how skilled individuals become.

## Core functions, regardless of size

| Function | What it looks like small | What it looks like at scale |
|---|---|---|
| Pattern library | A shared doc of prompt templates and processes | A maintained internal tool/repository |
| Training | One person running occasional sessions (Module 5) | A structured onboarding + ongoing curriculum |
| Governance liaison | Flagging policy gaps to whoever owns policy (Module 3) | A dedicated seat in policy decisions |
| Measurement | A few people tracking impact informally (Module 4) | Standard metrics reported org-wide |
| Support | Answering questions in a shared channel | A staffed help function |

A CoE doesn't need to start at the right-hand column — it needs to start
doing all five functions at some level, even informally, rather than
doing one well and ignoring the rest.

## Starting small without waiting for a mandate

A CoE can start as one motivated person or a small volunteer group
collecting what's already working across the organization and making it
visible — this often works better than waiting for a formal charter,
because it builds credibility through actual usefulness before asking
for authority. The formal structure, if it comes, follows demonstrated
value rather than preceding it.

## Avoiding the two failure modes

- **Becoming a bottleneck**: if every AI-assisted workflow has to be
  approved by the CoE before use, adoption slows to a crawl and people
  route around it. The CoE's job is to make good defaults easy to find,
  not to gatekeep every use.
- **Becoming irrelevant**: a CoE that only produces documents nobody
  reads, without staying connected to what teams actually need, drifts
  into a compliance exercise. Regular contact with real users (via the
  measurement and support functions) keeps it grounded.

## How It Actually Works

The reason a pattern library is worth building at all, rather than
letting each person re-derive good prompts on their own, comes down to
how these tools actually consume instructions. Every request to an AI
system starts from zero — there's no persistent memory of what worked
last week's project, no accumulated experience across users unless
someone captures it explicitly. The model reads whatever text is placed
in its context window for that one exchange and nothing else; a
brilliant phrasing one person discovered stays trapped in that person's
head, or at best their chat history, unless it's written down somewhere
the next person can find and reuse it. A CoE's pattern library is, at
its core, an external memory substituting for the model's lack of one —
which is also why the library only stays useful if someone keeps curating
it as tools change, rather than functioning as a one-time reference.

The "avoid becoming a bottleneck" warning has a related mechanical
basis. Because each request to the model is independent and cheap to
run, the practical cost of AI-assisted work is concentrated almost
entirely in the human steps around it — writing the prompt, reviewing
the output, deciding whether to trust it. A CoE approval gate inserted
into that loop doesn't make any individual generation safer or better;
it just adds a queue in front of a process whose actual bottleneck was
never the model call. Contrast this with a pattern library or a shared
verification checklist, which reduces the review burden at the point
where the real cost lives, for every future user of that pattern, not
just the one who wrote it. That's the underlying reason "make good
defaults easy to find" scales better than "gatekeep every use" — one
intervention compounds across users and time, the other adds a fixed
tax to each individual use with no compounding benefit.

This is also why a CoE can genuinely start as one person: the leverage
doesn't come from headcount, it comes from converting one person's
verified, working process into a document a hundred other people can
each run through the same context-window mechanism themselves.

## Exercise

Sketch a minimal version of each of the five functions above,
appropriately scaled for your own organization or team as it exists
today — one realistic sentence per function describing who would do it
and how, starting from what already exists rather than an ideal you'd
need new headcount to build.
