# 05 · Using Claude for Analysis & Research Tasks

Beyond writing, Claude is often used to think through a problem, compare
options, or make sense of information — analysis and research tasks. This
module covers how to prompt for structured comparisons, how to ask for
reasoning you can actually check, and where to be careful (a preview of
Module 9's deeper look at limitations).

## Structured comparisons

A vague "what do you think" invites a vague answer. Naming the criteria you
actually care about produces something you can act on.

| Vague prompt | Structured prompt |
|---|---|
| "Should we use Tool A or Tool B?" | "Compare Tool A and Tool B on: setup time, monthly cost, and integration with our existing calendar system. Present as a table, then give a one-sentence recommendation for a 3-person team on a tight budget." |
| "What do you think of this plan?" | "Evaluate this plan against two criteria: (1) does it address the drop-off we saw in week 2, and (2) can it realistically be done with 2 engineers in 3 weeks? Flag anything that fails either test." |

## Asking for reasoning, not just a conclusion

For any analysis with real stakes, ask Claude to show its reasoning, not
just hand you a verdict. This does two things: it usually improves the
quality of the answer (working through steps tends to catch errors a
jumped-to conclusion wouldn't), and it gives you something concrete to
check rather than a bare assertion to either trust or distrust blindly.

| Conclusion-only prompt | Reasoning-first prompt |
|---|---|
| "Is this pricing model a good idea?" | "Walk through the pros and cons of this pricing model step by step, considering our customer base (price-sensitive small clinics), before giving a recommendation." |
| "Which of these two candidates is better for the role?" | "List the specific strengths and gaps of each candidate against the job requirements first, then explain which factors you weighted most heavily in your recommendation." |

**Worked example:**

> Prompt: "We're deciding between raising prices 10% across the board or
> introducing a new higher tier and leaving current pricing alone. Walk
> through the tradeoffs of each for a subscription product with high price
> sensitivity, before recommending one."
>
> A reasoning-first response would work through churn risk, revenue impact,
> customer perception, and implementation complexity for each option
> *before* landing on a recommendation — giving you visible logic to check
> against what you know about your own customers, rather than a single
> unsupported sentence.

## Using Claude to structure a research question

Even before you have information to analyze, Claude can help you sharpen a
fuzzy research question into something answerable.

| Fuzzy question | Sharpened with Claude's help |
|---|---|
| "What's going on with our churn?" | "Help me break down 'what's going on with our churn' into 4-5 specific, answerable sub-questions I could investigate with our data (e.g., time-to-churn by plan, churn by acquisition channel)." |
| "Is this market worth entering?" | "What are the main categories of evidence I'd want before deciding whether to enter this market — competitive landscape, unit economics, regulatory barriers, anything else? List them, don't answer them yet." |

This use of Claude — as a thinking partner for structuring the question
itself — is often more valuable than asking it to just answer a vague
question directly.

## Where to be careful

Analysis and research tasks are exactly where Claude's limitations (Module
9) matter most, because a wrong analysis can look just as confident and
well-organized as a right one.

| Situation | Caution |
|---|---|
| Asking for specific statistics, dates, or figures you can't independently verify in the moment | Treat as something to verify before relying on, especially anything time-sensitive |
| Asking it to analyze data you haven't actually given it | Be explicit about supplying the real data (Module 7) rather than letting it assume or estimate |
| Asking for a recommendation on something with real financial, legal, or safety stakes | Use it to structure your thinking, not as the final decision-maker |

## Cheat sheet: analysis & research prompts

| Goal | Prompt pattern |
|---|---|
| Compare options | Name the specific criteria, ask for a table, ask for a recommendation last |
| Get checkable reasoning | "Walk through step by step / show your reasoning before concluding" |
| Sharpen a fuzzy question | "Break this into specific sub-questions, don't answer yet" |
| Analyze real data | Paste or attach the actual data — don't let it guess at numbers you have |
| High-stakes decision | Use Claude to structure the tradeoffs; make the final call yourself, verifying key facts independently |

## Exercise

Pick a real decision you're weighing (work or personal — which tool to
adopt, which of two approaches to take, etc.). Write a structured comparison
prompt naming at least three specific criteria, and a follow-up asking for
step-by-step reasoning before a recommendation. Then write one sentence on
which specific claims in the eventual answer you would want to verify
yourself before acting on it.
