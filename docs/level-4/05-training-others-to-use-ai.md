# 05 · Training Others to Use AI Assistants Effectively

Once you're AI-fluent yourself, the next capability is teaching it —
and teaching this well is different from teaching most software, because
the hard part isn't the interface, it's the judgment (when to trust
output, how to verify it, how to write a prompt that gets a useful
answer). This module covers how to train others effectively, drawing on
what actually worked across Levels 1-3.

## Why demoing the tool isn't training

Showing someone the chat interface and a couple of impressive outputs
teaches them that the tool exists, not how to use it well. Most training
failures look like this: people leave the session excited, try one thing
that doesn't work as well as the demo, and quietly stop. Effective
training targets the actual skills from earlier levels — clear
prompting, verification habits, knowing what not to hand to AI — not
just tool familiarity.

## A training structure that works

1. **Start with their real task, not a generic example.** Ask what
   they'd actually use it for and build the session around that —
   relevance is what makes the skill stick.
2. **Teach the verification habit alongside the capability**, from the
   first session. Someone who learns to prompt well but not to check
   output has learned half the skill and will produce confidently wrong
   work.
3. **Give them a template to start from** (Level 1, Module 10 /
   Level 3, Module 8) rather than a blank prompt box — most people
   learn faster by adapting something that already works than by
   starting from nothing.
4. **Have them do it, not watch it.** Hands-on practice on their own
   task, with you available for questions, beats a longer lecture every
   time.
5. **Follow up after a week**, not just at the end of the session —
   the real failure points show up once they're using it unsupervised,
   and a quick check-in catches bad habits before they set.

## Matching the training to skill level

A one-size-fits-all session under-serves both ends: someone new needs
the basics of clear prompting and why verification matters at all;
someone already comfortable needs the harder material (multi-step
workflows, evaluating output systematically) or they'll disengage.
Where possible, ask a couple of screening questions up front and route
people to the right starting point rather than running everyone through
the same script.

## Common mistakes when training others

- Over-selling capability, which sets people up to trust output they
  shouldn't, and under-mines credibility the first time it's wrong.
- Skipping the failure modes — not showing what confidently-wrong output
  looks like leaves people unprepared to recognize it.
- No follow-up, so early bad habits (skipping verification, copy-pasting
  output unreviewed) go uncorrected until they cause a real problem.

## How It Actually Works

Training on judgment, not interface, is the right focus specifically
because of where the underlying mechanism actually varies output quality —
and understanding that tells you exactly what to spend training time on.

**The interface has almost no effect on output quality; what's in the
prompt has almost all of it.** Clicking the right buttons doesn't change
what the model conditions on — a well-specified prompt typed into a
minimal chat box outperforms a vague one typed into the most polished
interface, because quality is entirely a function of clarity, context, and
specificity (Module 2, Level 1), none of which the interface supplies for
you. This is the direct, mechanistic reason demoing the tool (which
mostly showcases the interface and a couple of cherry-picked prompts)
teaches almost nothing transferable: it doesn't show the learner *why*
those particular prompts worked, which is the only part that generalizes.

**Judgment training works because it targets the two places where the
mechanism is genuinely unreliable and needs a human check: confident
plausibility standing in for correctness (Module 9, Level 1), and
generation standing in for judgment it can't supply (Module 4, Level 3).**
Effective training builds pattern-recognition for exactly those two
failure modes — teaching someone to notice when an answer is suspiciously
fluent about something they should verify, and when a task actually needed
their own accountable decision rather than a draft — which is a
transferable skill in a way that "here are the buttons" never is.

## Exercise

Plan a 30-minute training session for one real colleague on one real
task of theirs. Write down: the task you'd use as the example, the one
verification habit you'd insist they leave the session with, and the
one question you'd ask a week later to check whether it stuck.
