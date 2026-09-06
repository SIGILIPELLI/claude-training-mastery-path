# 09 · Common Prompting Mistakes & How to Fix Them

This module is a diagnostic reference: recognizable prompting mistakes,
why they produce the output they do, and the specific fix — useful both
as a checklist for your own prompts and for spotting why a colleague's
prompt isn't working.

## Mistake 1: Vague success criteria

**Symptom:** The output is "fine" but not quite what you wanted, and you
can't articulate exactly what's wrong with it.

**Cause:** The prompt never stated what a good answer looks like, so
Claude had to guess your bar.

**Fix:** State the acceptance criteria explicitly — length, tone, what
must be included, what must be excluded — before asking for the output,
not after seeing a miss.

## Mistake 2: Burying the actual instruction in context

**Symptom:** Claude answers a different question than the one you meant,
or answers the wrong part of a long message.

**Cause:** A long prompt with background, examples, and the actual ask
mixed together makes it easy for the real instruction to get less weight
than it deserves.

**Fix:** Put the instruction first or last (both are stronger positions
than the middle), and make it a clearly separated sentence: "Your task:
..." 

## Mistake 3: Asking for everything in one shot

**Symptom:** A complex, multi-part request comes back shallow on every
part, or fully addresses only the first part.

**Cause:** Cramming "write the report, then critique it, then suggest
three alternatives, then format it as a slide outline" into one prompt
spreads effort thin across four different jobs.

**Fix:** Split into sequential prompts, reviewing and correcting each
stage before moving to the next. This is slower per-step but faster
overall because you're not discovering a problem in step 1 after step 4
is done.

## Mistake 4: No worked example when format matters

**Symptom:** The output technically matches your description but not the
convention you actually wanted (wrong terseness, wrong tone, wrong
implicit format rule you didn't think to state).

**Cause:** Some conventions are much easier to show than describe.

**Fix:** Add one concrete example (few-shot, covered in Module 1) instead
of adding more adjectives to the description.

## Mistake 5: Treating a single response as final

**Symptom:** Settling for an 80%-good first response because asking again
feels like starting over.

**Cause:** Not realizing that a follow-up correction is cheap and Claude
retains the conversation context.

**Fix:** Treat the first response as a draft. "Keep everything the same
but make section 2 more concise" is a normal, cheap follow-up — use it.

## Mistake 6: Not separating instructions from pasted content

**Symptom:** Claude follows something inside a pasted document or email
as if it were an instruction to it, rather than treating it as inert data.

**Cause:** No clear boundary marker between "do this" and "here is the
material to do it on," especially risky with content from outside your
own team.

**Fix:** Use explicit delimiters (as in Module 1) and state plainly that
content inside them is data, not instructions.

## Mistake 7: Accepting a confident wrong answer

**Symptom:** A specific fact, citation, or number turns out to be wrong
after you've already used it.

**Cause:** Fluent, confident phrasing is not evidence of accuracy — this
is the single most consequential prompting mistake because it's invisible
at the moment it happens.

**Fix:** Apply the verification workflow from Module 6 to anything
specific and checkable before relying on it.

## Mistake 8: Re-explaining the same context every message

**Symptom:** Every prompt in a session re-states background that was
already established two messages ago, wasting effort and sometimes
introducing small inconsistencies between restatements.

**Cause:** Not trusting (or not using) the conversation's existing
context.

**Fix:** Reference what's already established ("using the same criteria
as above, now do X") instead of retyping it — but do restate anything
genuinely critical if the conversation has gotten long enough that early
instructions may be getting less weight.

## A pre-send checklist

Before sending a non-trivial prompt, a quick self-check:

- Is the actual instruction unambiguous and easy to find in the message?
- Have I said what "good" looks like, not just what topic to cover?
- If format matters, would an example help more than more description?
- Is pasted content clearly marked as data, not instruction?
- Am I asking for one coherent job, or secretly four?

## How It Actually Works

Each mistake above has the same mechanistic root: it under-specifies or
mis-positions the tokens the model conditions on. Seeing that pattern makes
new, unlisted mistakes easier to diagnose on your own.

**Mistakes 1, 3, and 4 are all forms of leaving the target distribution too
wide.** Vague success criteria, an unstated example format, and cramming
several unrelated asks into one instruction all leave the model with a wide
range of plausible, "reasonable-looking" continuations to choose among —
and it will pick one, but not necessarily yours, because nothing in context
narrowed the distribution toward your specific bar.

**Mistake 2 is about attention, not intent.** Burying the actual
instruction in the middle of a lot of context doesn't mean Claude "misses"
it in a human sense — the instruction tokens are still there and still
attended to — but they compete for weight against everything surrounding
them, so a critical instruction stated once, quietly, mid-paragraph, has
measurably less influence on the final tokens than the same instruction
stated clearly and positioned prominently (often near the start or the very
end of the prompt, which tends to get disproportionate weight).

**Mistake 5 misunderstands what a single response actually is: one sample
from a distribution, not a deterministic verdict.** Since generation
involves sampling from a probability distribution at each step, the same
prompt run twice can legitimately produce different results — treating one
draw as final skips the cheap, high-value step of asking for a second pass
or a revision (Module 8, Level 1).

**Mistake 6 is the data/instruction confusion from Module 1 of this level**
— without a clear boundary, tokens from pasted content can be attended to
as if they were part of the instruction, especially if the pasted content
itself contains imperative-sounding language.

**Mistake 7 is the hallucination mechanism from Module 9 (Level 1)** in
practice: fluency and correctness are optimized together but are not the
same thing, so a wrong answer can be exactly as confident-sounding as a
right one.

**Mistake 8 wastes context-window budget re-stating what's already sitting
in the transcript** (Module 3, Level 1) — the model already has access to
everything said earlier in the same conversation, so re-explaining it
doesn't add new conditioning, it just uses up window space that could
otherwise hold new, useful information.

## Exercise

Find a prompt of yours (or a colleague's) that produced a disappointing
result. Match it against the eight mistakes above — which one(s) apply?
Rewrite the prompt fixing just that mistake, re-run it, and compare the
two outputs side by side.
