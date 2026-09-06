# 08 · Building Custom Instructions/Personas for Recurring Tasks

If you find yourself typing the same role, tone, and format instructions
at the start of every prompt for a recurring task, that's a sign to build
a reusable custom instruction (a "persona") instead of re-writing it each
time. This module covers how to design one that actually holds up across
many uses.

## What a persona is, concretely

A persona is a standing block of instructions — saved in a project's
custom instructions, a system prompt, or just a text snippet you paste —
that fixes the role, scope, tone, and output format for a recurring type
of task, so each individual request can be short.

**Without a persona**, every request re-specifies everything:
> "You're a senior copy editor for a B2B SaaS blog. Tighten this for
> clarity, keep it under 800 words, use active voice, no jargon, flag
> anything that sounds like an unverified claim. Here's the draft: ..."

**With a persona saved**, the same request becomes:
> "Edit this draft: ..."

because the role, constraints, and format are already established.

## What to include in a durable persona

| Element | Example |
|---|---|
| Role and scope | "You are a technical editor for internal engineering docs. You do not write new content, only edit for clarity and correctness." |
| Standing constraints | "Always flag unverified claims. Never remove code examples without asking." |
| Output format | "Return edits as a diff-style list: original sentence → revised sentence → one-line reason." |
| Tone/voice | "Direct, no marketing language, second person ('you') when addressing the reader." |
| What NOT to do | "Do not add new sections. Do not soften technical criticism into vague praise." |

The "what not to do" line is often the most valuable one — it's usually
the thing that goes wrong first without an explicit persona.

## Testing a persona before relying on it

A persona is only useful if it holds up across a range of real inputs, not
just the one example you tested it with. Before trusting it for recurring
use:

1. Run it against 3-4 genuinely different real inputs (not variations of
   the same one) — a short one, a long one, an unusually messy one.
2. Check specifically for drift: does it hold the format on input #4 as
   well as input #1, or does it slip back toward default behavior on
   harder inputs?
3. Tighten the wording anywhere it drifted, and re-test.

## Common persona failure modes

- **Too vague to constrain anything.** "Be helpful and professional" adds
  no information — it's the default behavior anyway. A persona should rule
  things *out*, not just describe a pleasant vibe.
- **Contradictory instructions.** "Be extremely thorough" and "keep it
  under 100 words" fight each other; Claude will resolve the contradiction
  somehow, but not predictably. Resolve it yourself.
- **Missing the edge case that actually shows up.** A persona written
  against one clean example often misses how to handle an empty input, a
  contradictory source document, or a request outside its stated scope.
  Add an explicit instruction for the edge cases you actually hit.

## Where personas live, by interface

- **Chat/app projects**: persistent project instructions or custom
  instructions apply to every conversation in that project.
- **Claude Code**: a `CLAUDE.md` file at the project root is read at the
  start of every session — ideal for conventions, tone, and guardrails
  specific to that codebase.
- **API-integrated tools**: a system prompt set by whoever configured the
  integration; if you don't control it, your leverage is in how you phrase
  each individual request instead.

## A minimal template

> "Role: [who Claude is acting as and for whom]
> Scope: [what this persona does and explicitly does not do]
> Format: [exact output shape]
> Always: [standing rules that apply to every response]
> Never: [the specific failure modes to guard against]"

## How It Actually Works

A persona is often described as Claude "adopting a role," but mechanistically
it's simpler and more literal than that — and knowing exactly what it is
explains both why personas work well and why they sometimes fail in
specific, predictable ways.

**A standing instruction is just context that's present on every single
turn, positioned early.** Whether it's called a system prompt, custom
instructions, or a saved persona, it works by being included in the token
sequence for every generation in that context — the model doesn't "load" a
persistent identity into some separate module; it re-reads the persona text
fresh, alongside everything else, every time. This is why a persona that's
vague or self-contradictory produces inconsistent behavior across
sessions: there's no memory of "how it interpreted this last time" to fall
back on, so each session's interpretation is freshly derived from the same
(possibly ambiguous) text.

**Persona instructions compete with user turns for attention, and recency
matters.** Because attention weighs all context but real-world behavior
shows a bias toward more recent tokens carrying more influence on the very
next prediction, a persona's standing rules can get outweighed later in a
long session by an explicit, specific user request that contradicts it —
this is exactly why "common persona failure modes" include personas that
get overridden or "drift" over a long conversation, and it's also why
positioning matters: a system-level instruction slot (kept structurally
separate and re-supplied each turn by the product) resists this drift much
better than a persona buried once at the top of a single long chat.

**Testing a persona before relying on it works because it surfaces
edge-of-distribution behavior early.** A persona description is itself just
a prompt, subject to the same specificity principle as any other (Module 2,
Level 1) — an instruction like "be helpful and professional" is vague
enough that its actual effect on generation is hard to predict without
testing across several realistic inputs, because "professional" pulls
toward different plausible continuations depending on what surrounding
task-specific tokens happen to be in context at the time.

## Exercise

Identify a task you ask Claude to do at least weekly with roughly the same
role/format/tone each time. Write a persona using the template above.
Test it against three genuinely different real inputs for that task, note
any drift, and tighten the wording once based on what you found.
