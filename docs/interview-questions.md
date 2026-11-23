---
title: "Claude Training Interview Questions and Answers (179 Questions)"
description: "179 Claude Training interview questions with answers and explanations, from beginner to advanced, organised by level. Free, from the Claude Training Mastery Path."
---

# Claude Training Interview Questions and Answers

**179 questions** with the correct answer and a short explanation, organised from beginner (Level 1) to advanced (Level 4). Every question comes from a lesson in the free Claude Training Mastery Path, so you can open the lesson to go deeper.

!!! tip "Practise, don't just read"
    Each lesson also ends with an interactive quiz, and the [final quiz](quiz.md) tests all four levels. Try to answer each question below before reading the answer.

## Level 1 · Entry

### [01 · What Is Claude?](level-1/01-what-is-claude.md)

**Q1.** Your colleague says Claude 'looks things up' as it answers. What's the accurate picture?

**Answer:** Without a connected search or document tool it generates text from patterns learned in training; it isn't checking a live source

Plausible-sounding text isn't a guarantee of truth.

**Q2.** Which kind of task is Claude generally good at?

**Answer:** Drafting, editing, summarizing, explaining and analysing text

Know the edges as well as the strengths.

**Q3.** Why does the course avoid naming exact model versions or prices?

**Answer:** They change over time, so check the current documentation for precise details

The course is independent and not produced by Anthropic.

**Q4.** Is this course an official Anthropic product?

**Answer:** No: it's an independent educational resource

It says so explicitly.

### [02 · Writing Your First Effective Prompts](level-1/02-writing-effective-prompts.md)

**Q5.** Which prompt is more effective?

**Answer:** 'Summarize this report in five bullets for a busy CFO, focusing on cost risks'

It states audience, format, length and focus.

**Q6.** What problem does adding context solve?

**Answer:** Claude doesn't know who you are, what you've tried or what good looks like for you

Imagine briefing a new coworker.

**Q7.** What does clarity fix?

**Answer:** Claude answers the literal words, not the intent in your head

Ask whether someone else could tell what you want.

**Q8.** What does specificity add?

**Answer:** Format, length, audience and constraints that avoid a generic, average answer

Vague asks get vague results.

### [03 · Structuring a Conversation](level-1/03-structuring-a-conversation.md)

**Q9.** Do you need to re-explain background you gave earlier in the same conversation?

**Answer:** No, within the context window Claude can see everything said so far

Subject to context-window limits.

**Q10.** Claude's draft is 80% right. What's the efficient move?

**Answer:** Say what to keep and what to change in a follow-up instead of starting over

Correct course within the thread.

**Q11.** When is restarting with a tight recap better than continuing?

**Answer:** When a long conversation has drifted or become inconsistent

Carry only the essential context forward.

**Q12.** What is a context window?

**Answer:** The amount of text Claude can consider at once

Long chats can exceed it.

### [04 · Using Claude for Writing Tasks](level-1/04-using-claude-for-writing-tasks.md)

**Q13.** What should a good draft prompt include?

**Answer:** Format, audience, tone, length and key points to include

Then react to the first draft rather than perfecting the prompt.

**Q14.** You want your own voice preserved while tightening. What do you ask?

**Answer:** Edit for concision and clarity but keep my tone and don't add new claims

Say what to preserve.

**Q15.** A summary should be tailored to what?

**Answer:** The decision or purpose it will support and the reader

Different readers need different summaries.

**Q16.** Why ask Claude to change tone with an example sentence?

**Answer:** It anchors 'tone' to something concrete instead of an adjective

Specific beats abstract.

### [05 · Using Claude for Analysis &amp; Research Tasks](level-1/05-analysis-research-tasks.md)

**Q17.** Which prompt gets an actionable comparison?

**Answer:** 'Compare A and B on setup time, monthly cost and calendar integration, in a table, then recommend for a 3-person team'

Name the criteria that matter.

**Q18.** Why ask Claude to show reasoning?

**Answer:** So you can check the assumptions and steps rather than accept a bare conclusion

Reasoning you can audit is more useful.

**Q19.** What's a risk when asking Claude for statistics?

**Answer:** It may produce plausible-looking figures that are wrong; verify against a source

Specific numbers are high-risk claims.

**Q20.** What can improve a recommendation?

**Answer:** Telling Claude your constraints and the decision being made

Context turns analysis into advice.

### [06 · Using Claude for Code-Adjacent Tasks](level-1/06-code-adjacent-tasks.md)

**Q21.** You inherit a spreadsheet formula you don't understand. A good use of Claude is to...

**Answer:** Ask it to explain the formula in plain language and then check an example by hand

Verify with a test case.

**Q22.** What should you do before running a Claude-written script on real data?

**Answer:** Test on a copy or sample and read what it does

First-draft code can be wrong.

**Q23.** Is programming experience required to benefit from code-adjacent help?

**Answer:** No: explaining, reviewing and drafting scripts are approachable without writing code yourself

Still, verify the output.

**Q24.** What should a code-review prompt include?

**Answer:** What the code should do, the language and what kind of issues you care about

Specific criteria give useful reviews.

### [07 · Giving Claude Documents &amp; Context](level-1/07-documents-and-context.md)

**Q25.** Why paste a document instead of describing it from memory?

**Answer:** Claude works from the real text instead of your possibly inaccurate recollection

Supply material, don't paraphrase it.

**Q26.** What is a limit of long-context handling?

**Answer:** Details in very long inputs can be missed or weighted unevenly, so ask targeted questions and check key facts

Point Claude at the relevant sections.

**Q27.** How should you mark where your instructions end and the document begins?

**Answer:** Use clear delimiters or labels such as 'Document:' and quotes

It avoids instructions inside the data being followed.

**Q28.** Do upload limits stay the same across Claude products?

**Answer:** No, they vary by product and change over time; check current docs

Concepts stay durable.

### [08 · Iterating &amp; Refining Outputs](level-1/08-iterating-and-refining-outputs.md)

**Q29.** Which revision request works best?

**Answer:** 'Structure is good; cut paragraph 2 in half; leave the rest as is'

Say what to change and what to keep.

**Q30.** A response is wrong in three places. What's a good approach?

**Answer:** List each issue explicitly, or fix one at a time and re-check

Specific feedback beats a generic complaint.

**Q31.** What mindset does the module recommend?

**Answer:** Treat the first response as a first draft

Iteration is the skill.

**Q32.** Why name what to keep?

**Answer:** Otherwise Claude may change parts you liked

Protect the good parts.

### [09 · Understanding Limitations &amp; Verifying Outputs](level-1/09-limitations-and-verification.md)

**Q33.** What is a hallucination?

**Answer:** A confident, fluent statement that is wrong or invented

Fluency isn't accuracy.

**Q34.** Which claims deserve the most checking?

**Answer:** Specific facts: numbers, dates, citations, names and quotes

These are most likely to be fabricated.

**Q35.** Claude gives a citation you can't find. What do you do?

**Answer:** Treat it as unverified and look for the real source; it may be invented

Never cite what you haven't confirmed.

**Q36.** When should you not rely on Claude at all?

**Answer:** High-stakes decisions needing accountability or facts you can't verify (legal, medical, safety)

Match scrutiny to the stakes.

### [10 · Project — Build a Personal Prompt Template Library](level-1/10-project-prompt-template-library.md)

**Q37.** What is a good prompt template?

**Answer:** A proven prompt with placeholders for the specifics of each use

Reuse beats reinventing.

**Q38.** How should you build the library?

**Answer:** From tasks you actually repeat, testing each on real examples

Start with your own recurring work.

**Q39.** What should each template record?

**Answer:** Purpose, the prompt, required inputs, example output and verification steps

It makes templates reusable by others.

**Q40.** When should you update a template?

**Answer:** When results show a recurring failure or the task changes

Treat them as living.

## Level 2 · Intermediate

### [01 · Advanced Prompting Techniques](level-2/01-advanced-prompting-techniques.md)

**Q41.** What does assigning a role do?

**Answer:** Narrows the answer space and shifts vocabulary, depth and assumptions

It's a style/perspective lever, not authority.

**Q42.** What are few-shot examples?

**Answer:** Sample input/output pairs that show the pattern you want

Show, don't just tell.

**Q43.** Why separate instructions from data with delimiters?

**Answer:** So text inside the data isn't mistaken for instructions

Structure improves reliability.

**Q44.** What is an explicit output contract?

**Answer:** A stated format/fields the answer must follow

It makes outputs consistent.

### [02 · Chain-of-Thought &amp; Step-by-Step Reasoning Prompts](level-2/02-chain-of-thought-prompts.md)

**Q45.** When is asking for step-by-step reasoning most useful?

**Answer:** Multi-step problems where errors can hide in the middle

It surfaces assumptions and catches errors.

**Q46.** How should you read the reasoning Claude shows?

**Answer:** Critically: check each step, since a fluent chain can still contain a wrong step

Reasoning you can audit.

**Q47.** What does asking for reasoning first, then a conclusion, help avoid?

**Answer:** Jump-to-conclusion pattern matching

Lay out considerations in order.

**Q48.** A calculation looks suspicious. What do you do?

**Answer:** Re-do the arithmetic yourself or with a tool

LLM arithmetic can slip.

### [03 · Using Claude for Long Documents &amp; Summarization Strategies](level-2/03-long-documents-summarization.md)

**Q49.** A contract summary for a negotiator and one for an executive should be...

**Answer:** Different: tailor each to the decision it supports

Say what the summary is for.

**Q50.** A document exceeds the context window. What's a sound approach?

**Answer:** Split into sections, summarize each, then synthesize the summaries (checking key details against the source)

Chunk and combine.

**Q51.** Why ask for quotes or section references in a summary?

**Answer:** So you can verify claims against the source

Traceability beats trust.

**Q52.** What's a risk of summarizing summaries?

**Answer:** Errors and omissions compound; spot-check against the original

Verify important points at the source.

### [04 · Structuring Outputs](level-2/04-structuring-outputs.md)

**Q53.** You need the same table every week. What do you do?

**Answer:** State the columns, order and sorting once in a reusable prompt

Explicit structure makes outputs diffable.

**Q54.** When asking for JSON output to feed a script, what should you also do?

**Answer:** Validate the JSON in your code, since a model can still produce malformed output

Treat model output as untrusted input.

**Q55.** Which instruction makes a fixed template reliable?

**Answer:** Give the template with field names and say to fill only those

Show the exact shape.

**Q56.** Why define how to handle missing data in an output contract?

**Answer:** So Claude says 'not found' instead of inventing values

It reduces fabricated fills.

### [05 · Using Claude for Brainstorming &amp; Ideation](level-2/05-brainstorming-ideation.md)

**Q57.** 'Give me 20 ideas' returns 20 near-duplicates. What fixes it?

**Answer:** Ask for range: specify different approaches or categories and label each

Range, not just quantity.

**Q58.** After brainstorming, what's the next step?

**Answer:** Narrow with explicit criteria, then pressure-test the survivors

Widen then narrow.

**Q59.** Why give constraints during brainstorming?

**Answer:** They steer ideas toward feasible options

Constraints make ideas usable.

**Q60.** How should you use ideas Claude generates?

**Answer:** As raw material for your judgment, not as vetted truth

You own the choice.

### [06 · Fact-Checking &amp; Source Verification Workflows](level-2/06-fact-checking-verification.md)

**Q61.** Can Claude verify a claim against current reality by itself?

**Answer:** Not without a live tool such as search or a connected document

Training data isn't live.

**Q62.** What are the highest-risk kinds of claims?

**Answer:** Specific numbers, dates, prices, version numbers and quotes

Verify these at the source.

**Q63.** A good verification workflow does what?

**Answer:** Extracts the factual claims, checks each against a source, and records the result

Asking 'are you sure?' isn't verification.

**Q64.** If Claude says it is sure, should you skip checking?

**Answer:** No: confidence isn't evidence

Models can be confidently wrong.

### [07 · Using Claude Across Different Interfaces](level-2/07-across-different-interfaces.md)

**Q65.** What are Projects in the chat interface for?

**Answer:** Attaching persistent context such as style guides and prior decisions

Where available.

**Q66.** What is Claude Code?

**Answer:** A terminal-based coding agent

Each surface suits different workflows.

**Q67.** Do prompting principles change across interfaces?

**Answer:** The core principles stay the same; workflow details differ

Clarity, context and verification still apply.

**Q68.** Where do you check current limits and features?

**Answer:** The current official documentation

Features change often.

### [08 · Building Custom Instructions/Personas for Recurring Tasks](level-2/08-custom-instructions-personas.md)

**Q69.** When should you build a persona?

**Answer:** When you keep retyping the same role, tone and format for a recurring task

Short requests then follow a standing block.

**Q70.** What belongs in a persona?

**Answer:** Role, scope, tone, output format and what to do when unsure

Define boundaries and fallbacks.

**Q71.** How do you know a persona holds up?

**Answer:** Test it on varied real inputs, including edge cases

One good result isn't enough.

**Q72.** What's a risk of an over-long persona?

**Answer:** Conflicting or ignored instructions; keep it focused

Prune and test.

### [09 · Common Prompting Mistakes &amp; How to Fix Them](level-2/09-common-prompting-mistakes.md)

**Q73.** Output is 'fine but not quite right' and you can't say why. What's the likely mistake?

**Answer:** Vague success criteria: the prompt never stated the bar

State acceptance criteria up front.

**Q74.** Which fix applies to stuffing five asks into one prompt?

**Answer:** Split it into steps or number the tasks clearly

Smaller steps are easier to check.

**Q75.** Why is skipping verification a mistake?

**Answer:** Plausible errors are the ones AI is most likely to make

Check high-stakes claims.

**Q76.** Why paste sensitive data casually?

**Answer:** It's a mistake: be deliberate about what you share

Privacy comes later in the course.

### [10 · Project — A Multi-Step Research Workflow Using Claude](level-2/10-project-research-workflow.md)

**Q77.** Why choose a real research question for the capstone?

**Answer:** A real question forces output good enough to hand to someone else

The exercise teaches only if stakes are real.

**Q78.** What's a sound order for a research workflow?

**Answer:** Define the question, gather sources, extract, synthesize, then verify

Stages with review points.

**Q79.** What makes the final output hand-off ready?

**Answer:** Claims traced to sources, uncertainty stated and a clear recommendation

It must survive scrutiny.

**Q80.** Where should a human review?

**Answer:** After each stage, before the next builds on it

Catch errors early.

## Level 3 · Advanced

### [01 · Advanced Context Management for Long Projects](level-3/01-advanced-context-management.md)

**Q81.** Why can long conversations degrade?

**Answer:** Earlier instructions get less weight and contradictory material accumulates

Manage context actively.

**Q82.** What's a practical fix for a drifting long project?

**Answer:** Start fresh with a tight recap or a standing project brief

A concise summary carries what matters.

**Q83.** What should a project brief contain?

**Answer:** Goal, decisions made, constraints, style rules and open questions

Curated, not exhaustive.

**Q84.** Why keep a running decision log outside the chat?

**Answer:** So key decisions survive restarts and don't depend on scrollback

It reduces re-litigation.

### [02 · Using AI for Complex Multi-Step Workflows](level-3/02-complex-multi-step-workflows.md)

**Q85.** Why split a big task into stages?

**Answer:** Each stage gives a review point so a wrong turn costs one stage, not the whole thing

One giant prompt hides dozens of judgment calls.

**Q86.** What should pass between stages?

**Answer:** A defined, checked output (a handoff artifact)

Clear interfaces reduce drift.

**Q87.** Where do humans belong in a workflow?

**Answer:** At checkpoints before costly or irreversible steps

Place review where errors are expensive.

**Q88.** What's a sign of a good workflow design?

**Answer:** Each step has a clear input, output and acceptance check

Test stage by stage.

### [03 · Prompt Iteration &amp; Systematic Testing of Prompts](level-3/03-prompt-iteration-testing.md)

**Q89.** A prompt works great on your one example. What next?

**Answer:** Test it on a small set of varied, realistic inputs including edge cases

It may fail on other common inputs.

**Q90.** What belongs in a prompt test set?

**Answer:** Typical cases, tricky cases and known past failures

Cover the real range.

**Q91.** After changing a prompt, what do you re-run?

**Answer:** The whole test set, to catch regressions

Fixes can break other cases.

**Q92.** How do you compare two prompt versions fairly?

**Answer:** Run both on the same inputs and judge against the same criteria

Same inputs, same rubric.

### [04 · Combining AI Assistance with Human Judgment](level-3/04-ai-assistance-human-judgment.md)

**Q93.** What should stay with a human?

**Answer:** Judgment needing accountability, values tradeoffs, missing context and responsibility for being wrong

Generation is cheap; judgment isn't.

**Q94.** Claude drafts a performance review. What's the right use?

**Answer:** Use it as a draft, apply your own knowledge of the person, and own the final text

Accountability stays with you.

**Q95.** Which decision shouldn't be delegated to AI alone?

**Answer:** One with legal, medical or safety consequences

Scale review to stakes.

**Q96.** What does 'human in the loop' mean in practice?

**Answer:** A person reviews and can override before the result takes effect

Meaningful review, not rubber-stamping.

### [05 · Using Claude for Learning New Skills/Subjects Effectively](level-3/05-learning-new-skills.md)

**Q97.** Which pattern builds durable understanding?

**Answer:** Ask Claude to quiz you, make you explain it back and correct your errors

Active recall beats passive reading.

**Q98.** What does the Feynman-style technique have you do?

**Answer:** Explain the concept in simple words and have Claude find gaps

Gaps show where to study.

**Q99.** Why verify what Claude teaches?

**Answer:** It can state wrong things confidently, especially specifics

Cross-check with authoritative sources.

**Q100.** What's a good learning prompt?

**Answer:** 'Teach me X at beginner level, then give me 5 practice questions and mark my answers'

Make yourself do the work.

### [06 · Team/Organizational Use of AI Assistants](level-3/06-team-organizational-use.md)

**Q101.** Why doesn't individual best practice scale to a team?

**Answer:** Not everyone internalizes it, so failures become inconsistent and hard to trace

Make good practice the path of least resistance.

**Q102.** What should a team share?

**Answer:** A library of tested prompts, a data-handling standard and review expectations

Avoid duplicated effort.

**Q103.** How do you reduce duplicated prompt-building?

**Answer:** Maintain a shared, versioned prompt library with owners

Central, tested, maintained.

**Q104.** What should teams define about pasting data?

**Answer:** A clear rule for what may and may not be pasted into prompts

Consistent standards prevent leaks.

### [07 · Privacy &amp; Data Handling Considerations When Using AI Tools](level-3/07-privacy-data-handling.md)

**Q105.** What may happen to input pasted into a consumer AI tool?

**Answer:** It may be retained or used to improve products depending on policy and settings

Check the provider's terms and plan.

**Q106.** Which data should you generally avoid pasting into a tool not approved for it?

**Answer:** Customer PII, credentials, confidential contracts and regulated data

Follow your organization's policy.

**Q107.** What's a safer practice before pasting?

**Answer:** Redact or anonymize identifying details

Minimize what goes in.

**Q108.** Do business tiers and consumer tiers have the same data terms?

**Answer:** Not necessarily: business/enterprise tiers often differ, so read the terms

Check what applies to your account.

### [08 · Building Repeatable AI-Assisted Processes](level-3/08-repeatable-ai-assisted-processes.md)

**Q109.** Why document a repeatable process?

**Answer:** Quality shouldn't depend on one person's memory on a given day

Externalize the know-how.

**Q110.** What belongs in a process document?

**Answer:** Inputs, prompts, review steps, owner and acceptance checks

So anyone can run it the same way.

**Q111.** How do you keep the process healthy?

**Answer:** Review it periodically against results and update it

Processes drift.

**Q112.** Who is accountable for the output of an AI-assisted process?

**Answer:** A named human owner

Assign ownership.

### [09 · Evaluating AI Output Quality Systematically](level-3/09-evaluating-output-quality.md)

**Q113.** Why isn't 'looks right' a real check?

**Answer:** Fluent text reads well whether or not it's correct, so errors are plausible

Surface plausibility is what wrong answers have.

**Q114.** What's a systematic evaluation method?

**Answer:** Score outputs against a rubric of criteria on a sample, with spot checks against sources

Define criteria before judging.

**Q115.** What does a good rubric include?

**Answer:** Accuracy, completeness, tone/format fit and risk of harm

Make it repeatable.

**Q116.** How should you sample outputs for review?

**Answer:** Include random, high-stakes and edge-case outputs

Don't only look at the easy ones.

### [10 · Project — Design a Team AI Usage Playbook](level-3/10-project-team-ai-playbook.md)

**Q117.** Why write the playbook for a specific team?

**Answer:** Real workflows and constraints force real decisions; abstract advice teaches nothing

Specificity makes it usable.

**Q118.** Which section is essential in a playbook?

**Answer:** Approved uses, data rules, review standards, owners and an escalation path

It ties together Level 3.

**Q119.** How should a playbook be rolled out?

**Answer:** Pilot, collect feedback, adjust, then expand

Adoption is a change problem.

**Q120.** How do you know the playbook works?

**Answer:** Check adherence and outcomes with simple metrics and review incidents

Measure, then revise.

## Level 4 · Master

### [01 · AI Literacy as an Organizational Capability](level-4/01-ai-literacy-organizational-capability.md)

**Q121.** When is a skill organizational rather than individual?

**Answer:** When it survives personnel turnover

If quality drops when the expert leaves, it was never institutionalized.

**Q122.** Three people use AI well and everyone else improvises. What does the org have?

**Answer:** A few AI-literate people, a fragile capability

Capability must belong to the organization.

**Q123.** What builds organizational capability?

**Answer:** Shared standards, training, examples, tools and feedback loops

Make it systemic.

**Q124.** What should AI literacy include for non-experts?

**Answer:** What AI can and can't do, verifying output and handling data safely

Literacy is judgment, not just usage.

### [02 · Change Management for AI Adoption](level-4/02-change-management-ai-adoption.md)

**Q125.** Why does AI adoption fail even with a good tool?

**Answer:** Human factors: unclear why, fear of replacement, misaligned incentives

The technology usually works.

**Q126.** How should leaders address fear of replacement?

**Answer:** Be honest about plans and show how roles change, with concrete commitments

Unaddressed fear produces quiet resistance.

**Q127.** What makes a pilot useful?

**Answer:** A real problem, willing participants, measured outcomes and a learning plan

Pilots build evidence.

**Q128.** What drives sustained adoption?

**Answer:** Showing people a concrete benefit to their own work

A clear 'why' for them.

### [03 · Responsible AI Use &amp; Governance Basics](level-4/03-responsible-ai-governance-basics.md)

**Q129.** What does governance add to personal discipline?

**Answer:** Written policy, ownership, review and accountability across the organization

Discipline must scale.

**Q130.** What should a basic AI use policy cover?

**Answer:** Approved tools, data rules, review requirements and incident reporting

Keep it clear and short enough to follow.

**Q131.** Who owns an AI-related incident process?

**Answer:** A named role responsible for triage and learning

Clear ownership speeds response.

**Q132.** Why classify use cases by risk?

**Answer:** So review and controls scale with potential harm

Low-risk drafts need less than high-stakes decisions.

### [04 · Measuring the Impact of AI-Assisted Work](level-4/04-measuring-impact-ai-assisted-work.md)

**Q133.** What's a weak way to measure AI impact?

**Answer:** Counting prompts or usage alone

Activity isn't outcome.

**Q134.** What should you measure alongside speed?

**Answer:** Quality, such as error rates and rework

Faster but worse isn't a win.

**Q135.** How do you estimate a real gain?

**Answer:** Compare against a baseline for the same task before and after

A baseline makes claims credible.

**Q136.** Why report uncertainty in impact numbers?

**Answer:** Small samples and self-reports can mislead; honesty maintains trust

Don't overclaim.

### [05 · Training Others to Use AI Assistants Effectively](level-4/05-training-others-to-use-ai.md)

**Q137.** What makes AI training stick?

**Answer:** Hands-on practice on the learners' own real tasks

Active practice beats passive explanation.

**Q138.** What's a good first module for beginners?

**Answer:** Clear prompts plus verifying output

Foundations first.

**Q139.** How do you assess whether training worked?

**Answer:** Observe changes in actual work output and errors

Behaviour change is the goal.

**Q140.** Why include examples of failure in training?

**Answer:** People need to see how plausible errors look

Calibration builds good habits.

### [06 · Staying Current as AI Capabilities Evolve](level-4/06-staying-current-ai-capabilities.md)

**Q141.** How do you keep up as capabilities change?

**Answer:** Follow official release notes and re-test your prompts and workflows periodically

Durable skills plus periodic re-tests.

**Q142.** Why re-test saved prompts after a model update?

**Answer:** Behaviour can change, silently breaking something that worked

Use your test set.

**Q143.** Which source is best for current feature details?

**Answer:** The provider's official documentation

Courses age.

**Q144.** What stays durable despite change?

**Answer:** Clarity, context, verification and human judgment

Principles outlast products.

### [07 · Ethical Considerations in AI-Assisted Work](level-4/07-ethical-considerations.md)

**Q145.** A team passes off AI-written work as entirely human-made where disclosure matters. What's the issue?

**Answer:** A transparency/honesty problem; follow the norms and policies for disclosure

Know when disclosure is expected.

**Q146.** AI is used to screen job applicants. What's a key risk?

**Answer:** Bias in outputs and decisions; require human review and testing for fairness

High-stakes decisions about people need extra care.

**Q147.** Who is responsible when AI-assisted work causes harm?

**Answer:** The people and organization that deployed and relied on it

Accountability can't be delegated to a tool.

**Q148.** What should you do if an output could affect vulnerable people?

**Answer:** Apply stronger review and consider whether to use AI at all

Scale care with potential harm.

### [08 · Building an AI Usage Center of Excellence](level-4/08-ai-center-of-excellence.md)

**Q149.** What does an AI Center of Excellence do well?

**Answer:** Maintains standards, shared tools and training and supports teams

An enabler, not a bottleneck.

**Q150.** What risk does a CoE face?

**Answer:** Becoming a gatekeeper that slows teams

Keep the mandate clear and advisory where possible.

**Q151.** What should a CoE publish?

**Answer:** Approved tools, tested prompt libraries, policies and case studies

Make good practice easy.

**Q152.** How should a CoE show value?

**Answer:** Through adoption quality and measured outcomes in teams it supports

Outcomes, not activity.

### [09 · Career Growth: Becoming an AI-Fluent Professional](level-4/09-career-growth-ai-fluent-professional.md)

**Q153.** What distinguishes an AI-fluent professional?

**Answer:** Using AI effectively while verifying, applying judgment and understanding limits

Fluency is judgment plus skill.

**Q154.** How do you demonstrate AI fluency?

**Answer:** Show examples of improved outcomes with documented process and verification

Evidence beats assertions.

**Q155.** Which skill grows in value as AI generates more drafts?

**Answer:** Evaluation and judgment

Someone must decide what's good.

**Q156.** How should you keep growing?

**Answer:** Practice on real work, reflect and share what you learn

Learning compounds.

### [10 · Capstone — Full Organizational AI Adoption Plan](level-4/10-capstone-ai-adoption-plan.md)

**Q157.** What does the adoption plan combine?

**Answer:** Literacy, change management, governance, measurement and training for an organization

The capstone ties Level 4 together.

**Q158.** What's the right order for rollout?

**Answer:** Pilot with measurement, learn, set governance, then scale with training

Evidence before scale.

**Q159.** How should the plan handle risk?

**Answer:** Classify use cases and match controls to risk

Proportionate governance.

**Q160.** How should success be judged?

**Answer:** Against baselines for outcomes and quality, with honest uncertainty

Don't overclaim.

## Mixed questions across all levels

**Q161.** Your first reply from Claude is 80% right. What's the most efficient next step?

**Answer:** Say what to keep and exactly what to change in a follow-up

Treat the first response as a draft.

**Q162.** A prompt says 'Write a summary of this report.' The output is generic. What's missing?

**Answer:** Purpose, audience, length and what decision the summary supports

Specificity and context fix generic answers.

**Q163.** You paste a 200-page contract and ask for 'the key risks'. What improves reliability?

**Answer:** Ask for risks per section with quotes or clause references, then spot-check them against the source

Traceable claims can be verified.

**Q164.** Claude gives a statistic with a citation you can't find. What should you do?

**Answer:** Treat it as unverified, find the real source or drop the claim

Fabricated citations look real.

**Q165.** You need the same weekly table every Friday. What's the best technique?

**Answer:** An explicit output contract: columns, order, sorting and what to write when data is missing

Explicit structure is reusable and diffable.

**Q166.** Brainstorming returns 20 near-identical ideas. How do you fix the prompt?

**Answer:** Ask for range: name different approaches and label each idea

Range, not quantity.

**Q167.** A long project chat has become inconsistent. What's a sound move?

**Answer:** Start fresh with a concise brief of goal, decisions and constraints

Manage context actively.

**Q168.** Why split a go-to-market task into research, plan and drafts?

**Answer:** Each stage has a review point, so a wrong turn costs one stage instead of everything

One giant prompt hides many judgment calls.

**Q169.** Your persona prompt worked on one example. Before the team relies on it, what do you do?

**Answer:** Run it on a small test set of varied and edge-case inputs

It can fail on equally common inputs.

**Q170.** After editing a prompt to fix one failure, a different case breaks. What process catches this?

**Answer:** Re-run the whole test set after every change to check for regressions

Fixes can break other cases.

**Q171.** A manager wants Claude alone to decide who gets a promotion. What's the right boundary?

**Answer:** Claude can help with drafts and analysis; a human owns the judgment and accountability

Generation vs judgment.

**Q172.** Which is the best way to use Claude for learning a new subject?

**Answer:** Have it quiz you, make you explain concepts back and correct your mistakes

Active recall builds understanding.

**Q173.** An analyst wants to paste customer emails and phone numbers into a consumer chat tool. What should happen first?

**Answer:** Check the data policy and redact or anonymize the personal details

Minimize what goes in.

**Q174.** A team of 20 uses AI inconsistently. What's the scalable fix?

**Answer:** A shared, versioned prompt library, a data-handling standard and review expectations

Make good practice the path of least resistance.

**Q175.** Output 'looks right' but a pricing claim is wrong. What does this show?

**Answer:** Fluent output can be plausible and still wrong; evaluate against a rubric and sources

Looks-right is the weakest check.

**Q176.** A pilot shows 30% faster drafts. What else must you measure before claiming success?

**Answer:** Quality: error rates and rework, against a baseline

Faster but worse isn't a win.

**Q177.** Employees fear AI will replace them and quietly avoid it. What's the right response?

**Answer:** Be honest about plans, show how roles change and give a concrete benefit for their own work

Fear is a change-management problem.

**Q178.** A model update changes how your saved prompts behave. What should you have in place?

**Answer:** A test set to re-run so you notice regressions

Re-test after model changes.

**Q179.** A CoE becomes 'the team we have to go through'. What went wrong?

**Answer:** It became a gatekeeper; refocus on enabling teams with standards, tools and training

Enable, don't block.

## Practical coding questions

### Redact personal data before prompting

Write redact(text) that replaces email addresses with [EMAIL] and phone numbers with [PHONE] before a support ticket is pasted into an AI tool, leaving short numbers such as order ids untouched.

Starter code:

```
import re

def redact(text):
    # replace email addresses with [EMAIL] and phone numbers with [PHONE]
    # (leave short numbers such as order ids alone)
    return text

ticket = ("Hi, I'm Dana (dana.lee@example.com). Please call +1 415-555-0142 "
          "or 020 7946 0958 about order 88231.")
print(redact(ticket))
```

Expected output:

```text
Hi, I'm Dana ([EMAIL]). Please call [PHONE] or [PHONE] about order 88231.
```

??? success "Show a solution"

    ```
    import re

    def redact(text):
        text = re.sub(r"[\w.+-]+@[\w-]+\.[\w.]+", "[EMAIL]", text)
        text = re.sub(r"\+?\d[\d\s().-]{7,}\d", "[PHONE]", text)
        return text

    ticket = ("Hi, I'm Dana (dana.lee@example.com). Please call +1 415-555-0142 "
              "or 020 7946 0958 about order 88231.")
    print(redact(ticket))
    ```

    Minimizing what goes into a prompt is the first privacy habit. A regex isn't a complete PII detector (names and addresses need other tools), but it's a cheap, testable first filter. Verified by running the solution.

### Score two prompt versions on a test set

Implement passes() (under 40 words, contains the required keyword, no banned phrase) and pass_rate_v(index). Compare prompt versions v1 and v2 on the test set and list regressions, the cases that passed with v1 but fail with v2.

Starter code:

```
# Each test case: (name, output_from_prompt_v1, output_from_prompt_v2). The rubric checks
# that an answer is under 40 words, contains a required keyword and has no banned phrase.
CASES = [
    ("refund",   "We will refund you within 5 days. Sorry for the trouble.", "Refund issued. It arrives within 5 days."),
    ("shipping", "Your parcel ships Monday and arrives Wednesday.", "Probably ships soon, I think."),
    ("outage",   "As an AI I cannot confirm an outage; check the status page.", "Check the status page for outage updates."),
]
REQUIRED = {"refund": "refund", "shipping": "ships", "outage": "status page"}
BANNED = ["as an ai", "i think", "probably"]

def passes(name, text):
    # True when text is under 40 words, contains REQUIRED[name] and none of BANNED
    return False

def pass_rate_v(index):
    # share of CASES whose output at tuple position `index` passes
    return 0.0

v1, v2 = pass_rate_v(1), pass_rate_v(2)
print("v1: %.0f%%" % (v1 * 100))
print("v2: %.0f%%" % (v2 * 100))
print("failing in v2:", [c[0] for c in CASES if not passes(c[0], c[2])])
print("regressions:", [c[0] for c in CASES if passes(c[0], c[1]) and not passes(c[0], c[2])])
```

Expected output:

```text
v1: 67%
v2: 67%
failing in v2: ['shipping']
regressions: ['shipping']
```

??? success "Show a solution"

    ```
    # Each test case: (name, output_from_prompt_v1, output_from_prompt_v2). The rubric checks
    # that an answer is under 40 words, contains a required keyword and has no banned phrase.
    CASES = [
        ("refund",   "We will refund you within 5 days. Sorry for the trouble.", "Refund issued. It arrives within 5 days."),
        ("shipping", "Your parcel ships Monday and arrives Wednesday.", "Probably ships soon, I think."),
        ("outage",   "As an AI I cannot confirm an outage; check the status page.", "Check the status page for outage updates."),
    ]
    REQUIRED = {"refund": "refund", "shipping": "ships", "outage": "status page"}
    BANNED = ["as an ai", "i think", "probably"]

    def passes(name, text):
        t = text.lower()
        return (len(text.split()) < 40
                and REQUIRED[name] in t
                and not any(b in t for b in BANNED))

    def pass_rate(version):
        results = [passes(name, outs[version]) for name, *outs in CASES]
        return sum(results) / len(results)

    def pass_rate_v(index):
        return sum(passes(c[0], c[index]) for c in CASES) / len(CASES)

    v1, v2 = pass_rate_v(1), pass_rate_v(2)
    print("v1: %.0f%%" % (v1 * 100))
    print("v2: %.0f%%" % (v2 * 100))
    print("failing in v2:", [c[0] for c in CASES if not passes(c[0], c[2])])
    print("regressions:", [c[0] for c in CASES if passes(c[0], c[1]) and not passes(c[0], c[2])])
    ```

    Both versions score 67%, yet v2 fixed the outage case while breaking shipping. Equal averages can hide regressions, which is why you re-run the whole test set and compare per case. Verified by running the solution.

---

More free practice: the [Claude Training Mastery Path](index.md) curriculum, the [Interview Prep Pack](https://learnmasterypath.com/interview-pack/) and the [free resume ATS check](https://learnmasterypath.com/resume/).
