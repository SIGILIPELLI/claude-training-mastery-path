# 02 · Change Management for AI Adoption

Introducing AI-assisted workflows into a team is a change-management
problem before it's a tooling problem: the technology usually works fine
in isolation, and adoption still fails, because the human factors around
it (trust, incentives, fear, unclear expectations) were never addressed.
This module covers what actually determines whether adoption sticks.

## Why AI adoption fails even when the tool is good

The most common failure modes aren't technical:

- **No clear "why"**: people are told to use AI tools without a
  concrete case for what problem it solves for *them*, so it reads as
  extra process rather than help.
- **Fear of being replaced**: unaddressed, this produces quiet
  resistance — people who technically comply but don't actually change
  how they work, or who feel threatened enough to undermine the effort.
- **No time carved out to learn**: adoption competes with existing
  workload; without protected time, people default to the way they
  already know.
- **Inconsistent signals from leadership**: if managers don't visibly
  use the tools or apply the standards themselves, "adopt AI" reads as
  something for other people to do.

## A framework for rolling out a change

Borrowing from general change management, adapted for AI adoption:

1. **Name the specific problem it solves**, for this team, concretely —
   not "AI will make us more efficient" but "this cuts the time on our
   weekly report from three hours to forty minutes."
2. **Show, don't tell**: a live demonstration on a real, familiar task
   beats a slide deck about AI capabilities in general.
3. **Start with volunteers, not mandates**: early adopters who succeed
   become credible internal advocates in a way a top-down mandate never
   is.
4. **Protect time to practice**: treat the learning curve as a real cost
   to budget for, not something that happens for free in the margins.
5. **Address the job-security question directly** rather than hoping it
   doesn't come up — silence reads as confirmation of the fear, not
   reassurance.
6. **Make the new way visibly the default** once it's proven — update
   the actual templates and checklists people use day to day, not just
   the guidance document nobody re-reads.

## Handling resistance

Resistance is information, not just an obstacle: someone pushing back
often has a specific, valid concern (accuracy on their particular task,
a data-handling worry, a bad first experience with a clunky prompt).
Treating resistance as something to overcome rather than something to
understand tends to produce the compliant-but-unconvinced outcome that
quietly reverts once attention moves elsewhere.

## How It Actually Works

Change-management failures around AI adoption are human problems, but one
of the most common ones is downstream of a real mechanistic fact worth
naming plainly: the tool is genuinely inconsistent at the edges, and
pretending otherwise is what erodes trust fastest.

**Trust breaks when people are told the tool is more reliable than the
mechanism actually supports.** Because output is generated from a
probability distribution rather than computed with guaranteed correctness
(Module 9, Level 1; Module 9, Level 3), a new user who is told "just trust
it" and then hits a confident, fluent, wrong answer on their first real
use doesn't just lose confidence in that one output — they generalize to
distrusting the tool entirely, often more harshly than the tool's real,
bounded unreliability warrants. A rollout that's honest about *where*
generation is strong (drafting, structuring, first-pass analysis) and
where it needs verification (specific facts, numbers, anything with real
stakes) sets an accurate expectation that survives contact with an
inevitable wrong answer, rather than one that collapses at the first one.

**Fear of being replaced is, mechanistically, a fear about which half of
the task the tool can actually do.** As Module 4 (Level 3) covered,
generation cannot substitute for judgment that depends on accountability,
values, or information the model was never given — framing adoption
honestly around that boundary (the tool handles generation, people keep
judgment) addresses the fear with an accurate technical claim, not just a
reassuring one.

## Exercise

Think of one AI-assisted workflow that would benefit a team you're part
of. Write a one-paragraph "why" pitch for it, aimed at the person doing
the work rather than at leadership — stated as a concrete before/after
on a specific, recognizable task, not as a general efficiency claim.
