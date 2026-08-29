# 08 · Iterating & Refining Outputs

The single habit that separates people who get a lot of value from Claude
from people who get a little is this: **treat the first response as a first
draft, not a final answer.** This module covers how to ask for revisions
effectively — being specific about what to change, what to keep, and how to
handle a response that's wrong in more than one place at once.

## The core skill: naming what to change and what to keep

A generic "make it better" gives Claude no signal about what "better" means
to you, and risks it changing things you were actually happy with.

| Vague revision request | Specific revision request |
|---|---|
| "Make it better." | "The structure is good, but the second paragraph is too long — cut it by half. Leave the rest as is." |
| "This isn't quite right." | "The tone is right, but you used the word 'leverage' twice and it doesn't fit our style — replace both instances with something plainer." |
| "Try again." | "Try again, but this time lead with the conclusion instead of building up to it." |

The pattern: identify the specific thing that's wrong, say what "right"
looks like, and explicitly protect what's already working so it doesn't get
rewritten unnecessarily.

## Handling multiple problems in one response

When a response has several issues at once, resist the urge to just say
"fix it" — list the issues, so each gets addressed rather than Claude
guessing which one you meant or over-correcting on just one.

**Worked example:**

> Response has three issues: too long, wrong tone for the audience, and
> missing a required disclaimer.
>
> Weak follow-up: "This isn't right, can you redo it?"
>
> Strong follow-up: "Three things: (1) cut this to half the length, (2) the
> tone is too casual for a legal audience — make it more formal, (3) you're
> missing the standard disclaimer about this not being legal advice — add
> it at the end."

Listing issues explicitly, even briefly, produces a much more reliable
second draft than a vague "this isn't right."

## Iterating toward a format or style

If you have a strong sense of the shape you want but can't fully specify it
up front, iterate toward it rather than trying to nail it in one prompt —
this is often faster than writing an exhaustive initial specification.

| Step | Example |
|---|---|
| 1. Rough first ask | "Give me a first draft of a project status update." |
| 2. React to what you got | "I like this structure — What's done / What's next / Blockers. Keep that, but make each section just 2 bullets max." |
| 3. Refine tone or detail | "Good. Now make the 'Blockers' section sound more urgent — right now it reads like a minor note, but it's actually holding up the launch." |
| 4. Lock it in as a template | "This format is exactly what I want going forward. Can you give me this as a reusable template with placeholders?" |

This "converge through iteration" approach is often more efficient than
trying to perfectly specify a format from a blank page — and step 4 (asking
for a reusable template) is the seed of the prompt library you'll build in
Module 10.

## When to revise vs. when to start over

| Signal | Move |
|---|---|
| The overall structure/approach is right, some details are off | Revise with specific instructions |
| The whole approach is wrong (misunderstood the goal) | Restate the goal clearly, possibly in a fresh message or fresh conversation, rather than layering fixes on a flawed foundation |
| You've made 4-5 rounds of small tweaks and it still isn't right | Consider whether your original prompt was actually specific enough (Module 2) — sometimes it's faster to rewrite the ask than keep patching the answer |

## Cheat sheet: revision requests

| Situation | What to say |
|---|---|
| One specific thing is wrong | Name it precisely, say what right looks like |
| Multiple things are wrong | List them as separate numbered points |
| You like the structure, want to adjust one part | Say explicitly what to keep unchanged |
| You're iterating toward an unclear target | Small steps, react to each, converge gradually |
| Same categories of fix keep coming up | Consider whether the original prompt needs more specificity, not more revision rounds |

## Exercise

Take an output you generated in an earlier module's exercise (or generate a
new short one now). Write three follow-up revision requests: one that names
a single specific change while protecting the rest, one that lists multiple
issues as numbered points, and one that asks Claude to turn the final
version into a reusable template. This last one is good practice for
Module 10's project.
