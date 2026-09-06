# 04 · Structuring Outputs

Getting Claude to return output in a specific, reusable shape — a table,
JSON, a fixed template — saves you the work of reformatting by hand and
makes outputs easy to diff, paste into other tools, or process
programmatically. This module covers how to specify structure reliably.

## Why structure requests need to be explicit

Left unconstrained, Claude will pick a reasonable format based on the
content — which is often fine, but not reusable if you need the same shape
every time (feeding a spreadsheet, a script, or a template). Specify the
exact structure once and reuse the prompt.

## Tables

State the columns, their order, and any sorting rule.

> "Return this as a markdown table with exactly these columns in this
> order: Task, Owner, Due Date (YYYY-MM-DD), Status (Not Started/In
> Progress/Done/Blocked). Sort by Due Date ascending. If Owner is unclear
> from the source, put 'Unassigned', don't guess a name."

Naming the sort order and how to handle missing data up front avoids a
second round-trip to fix formatting.

## JSON and other machine-readable formats

For output you'll feed into another tool, ask for the exact schema,
including types and what to do with nulls/missing fields.

> "Return a JSON array. Each object: `{"name": string, "amount": number,
> "date": "YYYY-MM-DD", "category": string}`. If a receipt doesn't show a
> category, use `"category": null` rather than guessing. Return only the
> JSON array, no surrounding prose."

The "return only the JSON, no surrounding prose" instruction matters —
without it, Claude may add a friendly sentence before or after that breaks
naive parsing. If you need to parse the result programmatically, also ask
it to wrap the JSON in a fenced code block (or explicitly not to) depending
on what your parser expects.

## Fixed templates

For recurring documents (status reports, meeting notes, incident
summaries), give Claude the literal template with placeholders and ask it
to fill it in — this is more reliable than describing the format in prose.

> "Fill in this template using the notes below. Keep every heading exactly
> as written, and if a section has no relevant content, write 'None this
> period' rather than omitting the heading.
>
> ```
> ## Status: [date]
> **Shipped this week:**
> **Blocked on:**
> **Next week:**
> **Risks:**
> ```"

## Headings, lists, and nesting

For longer structured output (a report, a plan), specify heading levels and
nesting depth if it matters to how the result will be consumed (e.g. pasted
into a doc with its own heading hierarchy):

> "Use `###` for top-level sections and `-` bullets under each — no further
> nesting. This will be pasted under an existing `##` heading in our wiki."

## Output contracts as a checklist

Treat every structure request as a checklist you can verify against the
actual output:

| Check | Example |
|---|---|
| Right columns, right order | Did it add an unrequested column? |
| Right sort | Is it actually sorted, or just grouped? |
| Right handling of gaps | Did it guess instead of flagging missing data? |
| Nothing extra | Did it add a summary paragraph you didn't ask for? |
| Parseable | If JSON, does it actually parse — no trailing commentary, no comments inside the JSON? |

Running this checklist on the first output from a new template is worth the
minute it takes — it's much cheaper than discovering the format is subtly
wrong after you've already fed 20 outputs into a script.

## How It Actually Works

Structured output formats aren't rendered by a separate formatting engine —
they're generated token by token like everything else, which explains both
why they usually work well and where they can subtly break.

**Valid JSON, tables, and markdown all emerge from the same next-token
process constrained by strong statistical patterns.** Training data
contains vast amounts of well-formed JSON, markdown tables, and templated
text, so once generation starts down one of those paths — say, an opening
`{` — the syntactically valid continuation (a quoted key, then a colon,
then a value) is overwhelmingly the most probable next tokens, because
that's the pattern seen almost universally in training. This is why
structure requests tend to be reliable: you're not fighting the model's
tendencies, you're aligning your request with an extremely well-reinforced
pattern.

**Errors in structure usually come from local, not global, prediction
mistakes.** Because generation is sequential and each token depends on
what came before, a single wrong token early in a structured block (a
missing comma, an unescaped quote inside a string) can cascade — every
token after it is now conditioned on an already-malformed sequence, and the
model may "recover" by producing something that looks locally plausible but
breaks strict parsing. This is why asking for simpler, more constrained
structures (a table over deeply nested JSON, for instance) tends to be more
reliably parseable: fewer opportunities for one early token-level slip to
propagate.

**A fixed template acts the same way examples do in few-shot prompting
(Module 1)** — by giving explicit token-level scaffolding to fill in rather
than asking the model to invent structure from a verbal description, you
reduce the space of plausible continuations to "the same shape, different
content," which is a much narrower and more reliable generation target than
"a well-organized response" left to the model's own judgment.

**None of this is validation.** Because structured output is still
generated probabilistically rather than produced by a strict grammar
enforcer (unless the specific product you're using adds explicit
constrained decoding or schema validation), a response that reads as valid
JSON should still be parsed and checked programmatically before being fed
downstream, not assumed correct because it looks right.

## Exercise

Pick a task you do repeatedly where the output should always have the same
shape (a status update, a data extraction, a comparison table). Write a
structure prompt with an explicit schema, sort rule, and a rule for missing
data. Run it twice on two different inputs and confirm the two outputs are
structurally identical — same columns/keys, same formatting — even though
the content differs.
