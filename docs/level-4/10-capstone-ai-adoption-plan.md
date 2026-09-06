# 10 · Capstone — Full Organizational AI Adoption Plan

This capstone combines every Level 4 module into one deliverable: a
written plan for adopting AI assistance across a real team or
organization, credible enough to actually propose to a decision-maker.

## The scenario

Use a real organization or team — your own, or one you know well enough
to make realistic assumptions. As with the Level 3 capstone, specificity
is what makes this exercise teach anything; a plan for "an organization"
in the abstract is not a plan, it's a template with the blanks unfilled.

## Step 1: Assess current maturity (Module 1)

Place the organization on the four-stage maturity curve (ad hoc, aware,
standardized, embedded), with concrete evidence for the placement — what
you actually observe, not what you'd hope to find.

## Step 2: Build the change-management case (Module 2)

Write the concrete "why" for the specific team or function you're
targeting first — a real before/after on a real task, not a general
efficiency claim — plus a plan for how you'll introduce it (start with
volunteers, protect time to learn, address the job-security question
directly).

## Step 3: Draft the minimum viable governance (Module 3)

Answer, in writing, the five governance questions from Module 3: what
data is off-limits, which tools are approved, what requires human review,
who owns the policy, and how concerns get reported. Keep it to a page.

## Step 4: Define how you'll measure impact (Module 4)

Pick two or three real metrics (time including review, error rate,
rework rate) for the pilot workflow from Step 2, and specify the
baseline you'll measure before rollout — not an estimate from memory.

## Step 5: Plan the training approach (Module 5)

Outline the first training session for the pilot group: the real task
it will center on, the verification habit it will insist on from day
one, and the one-week follow-up check.

## Step 6: Note the ethical and governance risk points (Modules 3, 7)

Identify the one or two places in this specific rollout where ethical
judgment (disclosure, fairness, impact on roles) or governance ambiguity
is most likely to come up, and state how you'd handle each if it does.

## Step 7: Sketch the ongoing structure (Modules 6, 8)

Describe, even minimally, who keeps this current after the pilot: who
re-tests assumptions as capabilities change (Module 6), and who plays
the center-of-excellence role of collecting and spreading what works
(Module 8) — this doesn't require new headcount, but it does require a
named owner.

## How It Actually Works

Several steps in this capstone lean on mechanisms covered earlier in the
course, and it's worth being explicit about why they matter at the
organizational scale rather than just the individual-task scale used in
earlier modules. The governance questions in Step 3 (what data is
off-limits, what requires human review) exist because of a structural
fact about how these systems process input: anything typed into a
prompt becomes part of the context the model conditions its response on
for that exchange, and depending on the product and its retention
settings, may also be stored, logged, or in some configurations used to
improve future models — there is no universal guarantee that pasted
text simply disappears after the response comes back. At individual
scale, one person can reason case-by-case about what feels safe to
paste. At organizational scale, dozens or hundreds of people making that
call independently, without a shared boundary, turns "probably fine"
individual judgments into a real aggregate exposure — which is exactly
why Step 3 asks for a written data boundary rather than trusting
distributed instinct.

The measurement plan in Step 4 matters for a related structural reason:
AI-assisted output is uniformly fluent regardless of how much genuine
verification went into it, so "it felt faster and better" is not a
reliable signal at either individual or organizational scale — it's
exactly the kind of impression fluent output reliably produces whether
or not it's accurate. A real baseline measured before rollout is the
only way to distinguish an actual time or error improvement from the
subjective feeling of one, which is why Step 4 insists on a measured
baseline rather than a remembered estimate.

Finally, the reason Step 7's ongoing-structure question is unavoidable
rather than optional: model capabilities genuinely change between
releases — new context window sizes, new tool-use behaviors, shifted
strengths and failure modes — so a workflow tuned to one model's
behavior can silently degrade in accuracy or drift stale as usage
patterns evolve, without any error message announcing it. An
organization that treats its AI adoption plan as a one-time rollout
rather than something with a named owner to re-test is choosing, whether
or not it says so explicitly, to let that drift go undetected.

## Deliverable

A single plan document (2-4 pages) covering: maturity assessment,
change-management case for the pilot, minimum viable governance,
measurement plan with baseline, training outline, key risk points, and
an ownership structure for what happens after the pilot. If at all
possible, share it with someone who has real authority over the team you
wrote it for and note their actual reaction — a plan that was never
tested against a real decision-maker's objections is still just a draft.

## What this capstone should make visible

Doing this end-to-end usually reveals that the hardest parts of
organizational AI adoption are not technical at all — they're getting
honest agreement on the data boundary, building genuine trust rather
than compliance, and committing to measure impact honestly, including
the costs. The individual skills from Levels 1-3 turn out to be a
prerequisite for this work, not a substitute for it.
