---
title: "Claude Training Cheat Sheet: Quick Reference, Beginner to Advanced"
description: "A free Claude Training cheat sheet: 10 quick-reference tables from every level of the Claude Training Mastery Path, each linked to its full lesson."
---

# Claude Training Cheat Sheet

Quick-reference tables from **10 lessons** of the free Claude Training Mastery Path, in course order from beginner to advanced. Each section links to the full lesson with explanations and runnable examples.

## Level 1 · Entry

### [01 · What Is Claude?](level-1/01-what-is-claude.md)

| Question to ask yourself | Why it matters |
|---|---|
| Does this task need very recent information? | If yes, plan to verify or supply that information yourself — don't assume Claude has it |
| Does this task need real domain expertise with real stakes (legal, medical, financial)? | Use Claude to think through it, not as the final decision-maker |
| Does this task depend on something specific to me or my organization? | Claude won't know it unless you tell it — plan to supply context (Module 7) |
| Is this a "generate a draft" or "verify a fact" task? | Claude is much stronger at the former; treat the latter with more scrutiny (Module 9) |
| Am I starting a new conversation? | Remember it has no memory of prior conversations unless the product you're using explicitly provides that |

### [02 · Writing Your First Effective Prompts](level-1/02-writing-effective-prompts.md)

| Check | Ask yourself |
|---|---|
| ✅ Clarity | Is there only one reasonable way to interpret this prompt? |
| ✅ Context | Have I included anything a new collaborator would need to know? |
| ✅ Audience | Have I said who this is for, if it matters? |
| ✅ Format | Have I said what shape the answer should take (list, table, prose, length)? |
| ✅ Tone | Have I said what tone fits, if the task is at all sensitive or brand-relevant? |
| ✅ Constraints | Have I flagged anything the answer must avoid or must include? |

### [03 · Structuring a Conversation](level-1/03-structuring-a-conversation.md)

| Situation | Move |
|---|---|
| Small tweak to the last output | Short, specific follow-up — don't restart the whole prompt |
| Output going the wrong direction | Name the specific problem, then redirect — don't just repeat the original ask |
| Big multi-part deliverable | Break into stages, checkpoint after each |
| Long thread getting confusing | Ask for a recap, or explicitly summarize decisions yourself |
| Need an independent take | Start a new conversation, not a follow-up in the same one |
| Switching topics entirely | Start a new conversation |

### [04 · Using Claude for Writing Tasks](level-1/04-using-claude-for-writing-tasks.md)

| Task | Key things to specify |
|---|---|
| Draft from scratch | Format, audience, tone, length, key points to include |
| Copyedit | "Don't change voice or meaning" (if that matters to you) |
| Tone shift | The target tone, and what to keep unchanged |
| Trim | Target length, what's most important to preserve |
| Restructure | The new order or structure you want |
| Summarize | Purpose of the summary, audience, format (bullets vs. prose), length |

### [05 · Using Claude for Analysis &amp; Research Tasks](level-1/05-analysis-research-tasks.md)

| Goal | Prompt pattern |
|---|---|
| Compare options | Name the specific criteria, ask for a table, ask for a recommendation last |
| Get checkable reasoning | "Walk through step by step / show your reasoning before concluding" |
| Sharpen a fuzzy question | "Break this into specific sub-questions, don't answer yet" |
| Analyze real data | Paste or attach the actual data — don't let it guess at numbers you have |
| High-stakes decision | Use Claude to structure the tradeoffs; make the final call yourself, verifying key facts independently |

### [06 · Using Claude for Code-Adjacent Tasks](level-1/06-code-adjacent-tasks.md)

| Goal | Prompt pattern |
|---|---|
| Understand unfamiliar code | "Explain step by step, assuming [your actual background]" |
| Review for issues | Name the specific category of concern (silent failures, edge cases, hardcoded values) |
| Generate a script/formula | Describe the goal precisely, ask for an explanation and any risks alongside it |
| Before running anything real | Ask "what could go wrong," test small first, keep an undo path |

### [07 · Giving Claude Documents &amp; Context](level-1/07-documents-and-context.md)

| Situation | What to do |
|---|---|
| You have the actual document | Supply it directly rather than summarizing it from memory |
| The document is long | Consider breaking it into sections, especially if quality seems to drop later in it |
| The document is incomplete | Say so explicitly, so Claude doesn't paper over the gap |
| Multiple documents | Label each clearly and state the specific comparison you want |
| One part matters most | Point to it explicitly rather than assuming it'll stand out on its own |

### [08 · Iterating &amp; Refining Outputs](level-1/08-iterating-and-refining-outputs.md)

| Situation | What to say |
|---|---|
| One specific thing is wrong | Name it precisely, say what right looks like |
| Multiple things are wrong | List them as separate numbered points |
| You like the structure, want to adjust one part | Say explicitly what to keep unchanged |
| You're iterating toward an unclear target | Small steps, react to each, converge gradually |
| Same categories of fix keep coming up | Consider whether the original prompt needs more specificity, not more revision rounds |

### [09 · Understanding Limitations &amp; Verifying Outputs](level-1/09-limitations-and-verification.md)

| If the output contains... | Do this |
|---|---|
| A specific number, date, or statistic | Verify against a real source before using it |
| A quote or citation | Confirm the source exists and says that |
| A claim about very recent events | Treat as possibly outdated or unconfirmed |
| A claim about Claude/Anthropic specifics (models, pricing, limits) | Check current official documentation |
| General structure, phrasing, brainstormed ideas | Lower risk — normal first-draft trust level applies |
| Anything going out under your name with real stakes | Full read-through and fact-check before it ships, regardless of format |

### [10 · Project — Build a Personal Prompt Template Library](level-1/10-project-prompt-template-library.md)

| Check | Question |
|---|---|
| ✅ Recurring | Is this a task I'll genuinely do again, not a one-off? |
| ✅ Placeholders | Are the variable parts clearly marked? |
| ✅ Fixed structure | Does the template lock in the format/tone that already worked? |
| ✅ Verify note | Does it flag what kind of claim in the output deserves a fact-check? |
| ✅ Tested | Have I run it with a real example, not just written it in theory? |

---

Go deeper with the full [Claude Training Mastery Path](index.md) curriculum or test yourself with the [interview questions](interview-questions.md).
