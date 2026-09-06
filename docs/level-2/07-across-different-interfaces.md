# 07 · Using Claude Across Different Interfaces

Claude shows up in several different surfaces — the web/app chat
interface, Claude Code (a terminal-based coding agent), API-integrated
tools inside other products, and browser extensions — and each changes
what a good workflow looks like even though the underlying model and
prompting principles stay the same. This module covers the practical
differences.

## The chat interface (claude.ai / mobile app)

Best for open-ended conversation, iterative writing, research, and
anything where you're thinking out loud alongside Claude. Practical notes:

- **Projects** (where available) let you attach persistent context — style
  guides, background documents, prior decisions — so you're not
  re-pasting the same material into every new conversation.
- **Conversation length matters.** Very long threads can dilute how much
  weight recent instructions carry relative to everything said earlier;
  for a task that's drifted or gotten confused, starting a fresh
  conversation with a tight recap is often faster than trying to
  course-correct deep in a long thread.
- **Artifacts/canvases** (where available) are useful for anything you'll
  iterate on visually — a document, a diagram, a small interactive
  prototype — since they keep the working version separate from the
  conversational back-and-forth.

## Claude Code (terminal-based coding agent)

Different mode entirely: Claude Code reads and edits files, runs shell
commands, and executes multi-step engineering tasks with your explicit
approval at the consequential steps. Practical notes:

- **A `CLAUDE.md` file at the project root persists instructions across
  sessions** — conventions, guardrails, how you want status reported —
  so you're not restating them every time.
- **It's an agent, not a chat.** You describe an outcome and it plans and
  executes multiple steps (reading files, writing code, running tests)
  rather than replying with just text. Reviewing what it's about to do
  before approving irreversible steps (deletions, pushes, deploys) is
  part of using it safely, not an inconvenience.
- **Good for anything with a verifiable outcome** — code that should pass
  tests, a build that should succeed — because you get an actual pass/fail
  signal instead of just a plausible-looking answer.

## Claude embedded in other products (via API)

Many tools embed Claude for a specific narrow purpose (support chat, an
in-app assistant, a specific automation). Here you usually don't control
the prompt directly — the product's developers wrote it — so your
leverage is different:

- **You control your own input**, so the clarity/context principles from
  Level 1 still help: a specific, well-scoped message gets a better
  response than a vague one, even inside someone else's wrapper.
  Interpretation.
- **Know the product's actual scope.** An embedded assistant is often
  configured to only answer within a narrow domain (e.g. your own
  product's documentation) — asking it something outside that scope will
  produce a worse answer than asking the same question in claude.ai
  directly, not because Claude is less capable but because it's been
  configured for a narrower job.

## Browser extensions and computer-use style tools

Where Claude can see and act on a live browser page (reading page
content, clicking, filling forms), the interaction becomes closer to
delegating a task than asking a question. Practical differences:

- **Confirm before consequential actions.** Submitting a form, completing
  a purchase, or posting something publicly should be reviewed before
  Claude executes it — treat this the same as you would a human assistant
  acting on your behalf for anything hard to undo.
- **Give it the destination and the constraint, not just the click.**
  "Find the cheapest flight matching these dates and show me the options"
  is a better instruction than narrating individual clicks — let the tool
  figure out the navigation, and you review the result.

## Choosing the right interface for the task

| Task | Best-fit interface |
|---|---|
| Drafting, editing, research, brainstorming | Chat / app |
| Writing or refactoring code across multiple files, running tests | Claude Code |
| A narrow, repeated task inside a product you already use | Embedded assistant |
| Filling out a web form, comparing options across live pages | Browser-driven tool, with confirmation on submit |

## How It Actually Works

Different interfaces feel like different products, but mechanistically
they're the same underlying model wired to different amounts of context
and different tools — that's what actually explains the practical
differences described above.

**The chat interface is closest to "raw" generation over conversation
history.** Its context window is mostly your messages and Claude's replies
(Module 3, Level 1), plus whatever you paste in — there's no standing
project state being tracked unless the surface explicitly supports it
(saved custom instructions, project knowledge). Every reply is still just:
re-read the transcript, predict the next tokens.

**Claude Code and other agentic surfaces add tool-calling round-trips
around the same core model.** Instead of generating only natural-language
tokens, the model can generate a structured "call this tool with these
arguments" output; the surrounding software actually executes that call
(reading a file, running a command), and the *result* gets inserted back
into context as new tokens before the model continues. This is a
fundamentally different information flow than chat: the model's context
now includes real, verified output from the outside world mid-task, not
just its own generated text — which is a big part of why agentic coding
tools can be more reliable on multi-step technical tasks than asking for
the same thing in a single chat turn.

**Products embedding Claude via API are shaping the context you don't
see.** A support tool or writing app built on the API typically injects its
own system prompt, relevant account data, or retrieved documents into
context before your message ever reaches the model — so the same words
typed into two different API-powered products can produce different
results not because the model changed, but because what's silently
sitting in context around your message did.

**Computer-use and browser-driving tools extend the same tool-call loop to
visual/interactive actions:** a screenshot or accessibility tree gets
encoded into context as the "observation," the model generates an action
(click, type, navigate), the environment executes it, and the resulting
new state is fed back in — round after round. The core mechanism (predict
next token, now including structured actions, from everything in context)
never changes; what changes across interfaces is only what's allowed into
that context and what the model is permitted to do about it.

## Exercise

Pick one task you currently do in chat that would actually be better
suited to a different interface (e.g. a coding task you're pasting code
for manually, or a repetitive web lookup). Try it in the more appropriate
interface and note concretely what became easier or more reliable, and
what you had to explicitly confirm or review that you wouldn't have in
chat.
