# 02 · Writing Your First Effective Prompts

A prompt is just the instruction or question you give Claude — but the gap
between a vague prompt and a clear one is the single biggest lever over
output quality you have as a user. This module covers the three ingredients
of an effective prompt — clarity, context, and specificity — with concrete
before/after examples for each.

## The three ingredients

| Ingredient | The problem it fixes | Question to ask yourself |
|---|---|---|
| **Clarity** | Claude answers the literal words you wrote, not the intent in your head | Could someone else read this prompt and know exactly what I want, with no guessing? |
| **Context** | Claude has no idea who you are, what you already tried, or what "good" looks like for you | Have I given Claude what it would need to know if it were a new coworker on this task? |
| **Specificity** | A vague ask gets a generic, average answer | Have I said what format, length, audience, and constraints I actually want? |

## Clarity: say exactly what you want

Vague prompts force Claude to guess at your intent, and it will guess at the
most generic, average interpretation — which is rarely what you actually
need.

| Vague prompt | Why it's weak | Improved prompt | Why it's better |
|---|---|---|---|
| "Write something about our product." | No topic focus, no purpose, no length | "Write a 3-sentence product description for our project-tracking app, aimed at small business owners, emphasizing ease of setup." | States topic, audience, length, and the one thing to emphasize |
| "Help me with this email." | Doesn't say what "help" means — write it? shorten it? make it firmer? | "Rewrite this email to be more concise and slightly more assertive, without sounding rude. Keep it under 100 words." | Names the specific transformation and a constraint |
| "Is this a good plan?" | "Good" against what standard? Good for what goal? | "Evaluate this plan against our stated goal of cutting onboarding time by 30% — where does it fall short?" | Gives a concrete evaluation criterion |

## Context: give Claude what a new coworker would need

Claude starts every new conversation with zero information about you, your
project, or your constraints (Module 1). If a fact would matter to a human
collaborator hearing this request for the first time, it matters to Claude
too.

| Prompt without context | Prompt with context |
|---|---|
| "Draft a message to the team about the delay." | "Draft a Slack message to a 6-person engineering team. The launch is delayed by one week because a third-party API we depend on changed its rate limits. Tone: matter-of-fact, not apologetic — this wasn't our error. Keep it under 80 words." |
| "Summarize this." | "Summarize this customer support transcript in 3 bullet points, focused on what the customer wants resolved — I'm going to hand this to the on-call engineer." |
| "What should our pricing be?" | "We sell a B2B scheduling tool to small clinics, currently priced at $49/month flat. We're considering a per-seat model. What tradeoffs should we weigh, given our customers are price-sensitive but hate unpredictable bills?" |

Notice the pattern: context isn't padding, it's the difference between a
generic answer and one actually usable for your situation.

## Specificity: name the shape of the output you want

Even a clear, well-contextualized prompt can produce an unhelpful shape of
answer if you don't say what shape you want.

| Under-specified | Specified |
|---|---|
| "Give me ideas for the onboarding flow." | "Give me 5 ideas for the onboarding flow, each as a one-line description plus one sentence on why it might reduce drop-off. Order them from lowest to highest engineering effort." |
| "Explain how this works." | "Explain how this works in 3 short paragraphs, for someone who understands basic business concepts but has no technical background. Avoid jargon or define it inline." |
| "Compare these two options." | "Compare these two options in a table with columns: Cost, Setup time, Ongoing maintenance, Best for. End with a one-sentence recommendation for a 5-person team." |

## Putting it together: a worked example

**Task:** you need a short announcement about a new feature.

**First attempt (vague):**
> "Write an announcement for our new feature."

This will produce a generic, forgettable announcement, because Claude has no
idea what the feature is, who reads it, or what tone fits your brand.

**Second attempt (clear + context + specificity):**
> "Write a 4-sentence announcement for a new 'auto-save' feature in our note-taking app. Audience: existing users who've complained about losing work. Tone: warm but not over-the-top — we're fixing a real pain point, not launching something flashy. End with one sentence on how to enable it (it's on by default, no action needed)."

The second version gives Claude everything it needs to write something you
could actually publish with light editing, rather than something you have to
rewrite from scratch.

## Cheat sheet: the pre-send checklist

| Check | Ask yourself |
|---|---|
| ✅ Clarity | Is there only one reasonable way to interpret this prompt? |
| ✅ Context | Have I included anything a new collaborator would need to know? |
| ✅ Audience | Have I said who this is for, if it matters? |
| ✅ Format | Have I said what shape the answer should take (list, table, prose, length)? |
| ✅ Tone | Have I said what tone fits, if the task is at all sensitive or brand-relevant? |
| ✅ Constraints | Have I flagged anything the answer must avoid or must include? |

## Exercise

Take one of the three tasks you wrote down in Module 1's exercise. Write:

1. A deliberately vague, one-line version of the prompt.
2. An improved version applying clarity, context, and specificity.
3. One sentence predicting how the two outputs would differ, before you
   actually try either one.

If you have access to Claude, run both prompts and compare the real outputs
against your prediction.
