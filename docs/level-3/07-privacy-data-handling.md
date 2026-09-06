# 07 · Privacy & Data Handling Considerations When Using AI Tools

Pasting information into an AI assistant is different from pasting it
into a search bar or a private notes app. What you paste may be
retained, may be used to improve models depending on the provider's
policy and your account settings, and is visible to the provider's
systems even when it isn't used for training. Good practice here isn't
about avoiding AI tools — it's about being deliberate about what goes
in.

## What actually happens to your input

The details vary by provider and plan, but the general shape is
consistent: consumer-tier accounts often permit use of conversations to
improve products unless you opt out; business/enterprise tiers
typically contractually exclude your data from training and apply
shorter retention windows. Never assume a default — check the specific
plan's data-handling terms before treating "business account" as
synonymous with "safe by default." The one universal fact worth
remembering: whatever the training policy, your input is still
transmitted to and processed by the provider's systems, so "will this
be seen by a system I don't control" is always yes.

## A practical sensitivity checklist

Before pasting something in, run it against a short mental checklist:

| Category | Examples | Default action |
|---|---|---|
| Public or already-shared | Published docs, open-source code, your own drafts | Fine to paste |
| Internal but low-sensitivity | Internal style guides, generic process docs | Usually fine — check company policy |
| Confidential business data | Unreleased financials, strategy docs, unannounced deals | Don't paste without explicit clearance |
| Personal data of others | Customer PII, employee records, health/financial data | Don't paste — anonymize or use synthetic data instead |
| Credentials/secrets | API keys, passwords, tokens | Never paste, even in "just testing" contexts |

When in doubt, treat the input like you would an email to an external
vendor: would you send this to a contractor you don't have a signed NDA
with? If not, don't paste it into a consumer-tier AI tool either.

## Anonymizing and redacting before pasting

Often the useful part of a document doesn't require the sensitive
part. Before pasting a customer support ticket, strip the name, email,
and account number and replace them with placeholders (`[CUSTOMER]`,
`[EMAIL]`) — the AI can still help you draft a response or diagnose a
pattern without ever seeing the real identifiers. This is usually a
30-second edit and removes the entire risk category for that
interaction.

## Company policy comes first

Individual judgment is a fallback, not a substitute, for an actual
company policy. If your organization has a stated rule about what can
and cannot go into AI tools (many now do), that rule governs — even if
you personally judge a specific case as low-risk. If no policy exists,
that's itself worth flagging to whoever owns data governance, rather
than each person independently improvising a risk threshold.

## Retention and account settings

Check what retention and training-opt-out controls your specific
account offers — many providers let you disable chat history or opt
out of using conversations for training. These settings meaningfully
change your risk profile and take a few minutes to configure once.
Revisit them when your usage changes (e.g., moving from personal
experimentation to handling real work data).

## When the tool has file or connector access

Tools that can read your files, email, or connected apps (not just
text you paste) raise the same questions at a larger scale — the
tool's effective visibility is whatever it's been granted access to,
not just what's in the current message. Before granting broad access,
scope it to what the task actually needs, and review what's connected
periodically rather than granting once and forgetting.

## How It Actually Works

Understanding what actually happens to a prompt end-to-end clarifies why
"just be careful what you paste" is the right rule rather than something
you can work around cleverly.

**At inference time, your input becomes tokens processed by running the
model — a real computation on real infrastructure, not something that
vanishes when the response finishes.** The text you send is converted to
tokens, passed through the model's layers to generate a response, and
depending on the provider's retention policy and your account settings,
the raw input and output may also be logged or stored for abuse
monitoring, product improvement, or (on some plans) potential use in
future training — the specifics vary by provider and plan and change over
time, which is exactly why this module points you to current policy rather
than asserting fixed numbers here.

**Training, if it happens on a given account tier, works by incorporating
patterns from stored conversations into a future model's learned
weights** — a fundamentally different (and much less reversible) fate than
being merely stored: once information has influenced trained weights, it
can't be "deleted" the way a stored file can, because it no longer exists
as a discrete, extractable record — it's diffused into statistical
parameters shared across all future outputs of that model. This is the
mechanistic reason retention settings and training opt-outs are two
genuinely different levers, not one.

**Anonymizing before pasting works because the model can only condition on
the tokens it actually receives.** Replacing a real name or account number
with a placeholder before sending removes that specific information from
what's processed and potentially retained, while still letting the
model's generation be conditioned on everything else that's actually
relevant to the task — you're deliberately shaping context to include what
you need and exclude what you don't, the same context-management principle
from Module 1, applied to sensitivity rather than relevance.

**Connector and file access extends what's "sent" beyond what you typed.**
When a tool can read a connected drive or inbox, whatever it retrieves
becomes context the same way pasted text does — it's processed and
potentially logged the same way, which is why the sensitivity checklist
needs to apply to what a connected tool *can* access, not only to what you
manually paste.

## Exercise

Take a real task you'd like AI help with that involves data you were
hesitant to paste in directly. Redact or synthesize the sensitive
parts, get the assistance you need on the sanitized version, and note
whether the output was still useful. If it wasn't, that's a sign the
redaction removed information the task actually needed — which itself
tells you the task requires a business-tier tool with proper data
protections, not a workaround.
