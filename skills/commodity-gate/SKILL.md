---
name: commodity-gate
description: |
  Gate any TAP user-facing copy (page, post, email, ad, headline, lead magnet, video script) against three checks
  designed to keep TAP non-commodity: opinion, primitive, founder voice. Run this BEFORE publishing or scheduling.

  MANDATORY auto-chain: any time tap-content-atomiser, social, copywriting, copy-editing, email-sequence, cold-email, or liberty-press-release is about to land final copy, this skill fires FIRST. Hard rule: no TAP-facing copy publishes without a commodity-gate pass.
  Trigger phrases: "commodity-gate", "commodity check", "is this commodity", "is this commoditised", "is this generic", "does this differentiate", "is this on-brand", "founder voice check", "opinion check", "primitive check", "before publish", "before schedule", "before ship", "ready to publish", "ready to schedule", "publish-ready", "is this ready", "before posting", "/commodity-gate".
allowed-tools:
  - Read
  - Write
  - Edit
  - Grep
  - Bash
metadata:
  author: chrisschofield
  version: "1.0"
  added: 2026-04-30
---

# Commodity Gate

The premise: **AI made the software a commodity. The moat is what only TAP can say.**

Generic CRMs, contact-discovery tools, music-PR platforms, and LinkedIn-template carousels all converge on the same shape. If TAP copy could appear under a competitor's logo with no other change, it is commodity copy and should not ship.

This gate exists to catch that before publish.

## When to run

Before any of these reaches the queue, the page, or the inbox:

- LinkedIn / X / Threads / Instagram posts
- Newsletter issues
- Homepage, pricing, /compare/*, /for/*, /calculator/*, /about copy
- Cold outreach emails to PR agencies (Simon, Plus, Liberty network)
- Ad copy for Meta / LinkedIn paid
- Video scripts for HyperFrames reels
- Lead magnet body copy
- Any new section of the brand platform / docs that's customer-visible

If the work is internal-only (engineering notes, agent prompts, internal SQL), skip this gate.

## The three checks

A piece of copy must pass **all three**. Failing one means rewrite, not ship.

### 1. Opinion check

> Does this say something a generic CRM, Muck Rack, Submithub, or generic music-PR tool **cannot** say without lying?

Examples that pass:
- "Sending happens after explicit per-message human approval. No batch sends, no agent-only sends."
- "Spreadsheets work for one campaign. The break point is the second campaign." (specific to small-agency workflow)
- "TAP refuses to be a CRM because contacts are people you'll pitch to for years, not leads."

Examples that fail:
- "The all-in-one platform for music PR." (any platform could say this)
- "Powerful contact intelligence." (every tool has this)
- "AI-powered campaign management." (commodity AI hype)
- "Save time on outreach." (universal SaaS promise)

### 2. Primitive check

> Does the copy use at least one TAP-owned term, or set up a new one?

Current TAP-owned primitives:
- **The 5 objects**: Artists, Campaigns (with Pitches), Contacts, Activity, Home
- **Relationships are the product**
- **Campaign memory** (compound intelligence across campaigns)
- **Approval queue** (per-message human approval gate)
- **Send doctrine** (no batch / agent-only / DMARC-reject sends)
- **Second campaign break** (the spreadsheet failure point)
- **Working memory** (vs. spreadsheets that store but don't help you find)

If the copy uses none of these and doesn't introduce a new TAP-owned term, prefer adding one over shipping bland copy. New primitives must be specific, named, and repeatable across content.

Generic terms that should NOT count as primitives:
- "pipeline", "dashboard", "insights", "CRM", "platform", "workflow", "solution" (already banned per voice-gate)
- "AI assistant", "automation", "intelligence" (commodity AI hype)
- Any term that sits comfortably under a competitor's logo

### 3. Founder voice check

> Is this in Chris's first-person voice, or generic third-person SaaS-speak?

Voice gate (`scripts/social/postiz/voice-gate.py`) already catches the worst patterns at HARD level: aphorism pairs, negation-assertion, em-dashes, "genuinely / truly / really", LLM clichés. This check goes further:

- Is it specific to a real campaign, contact, station, or moment? (or generic / hypothetical?)
- Could Chris say this sentence aloud in conversation? (or only in a deck?)
- Is the subject "I / we / my / our" or "this product / users / customers"?
- Does it pass the "Brighton spreadsheets" test: would Chris on a quiet Tuesday writing about his own work produce this sentence?

Pass: "Five years of spreadsheets. I thought I had a system."
Fail: "Many music PR professionals struggle with disorganised contact data."

## Workflow

```
1. Read the draft copy.
2. Run voice-gate.py if it's a social post (catches base-level fails).
3. Score against the three checks above. Output: PASS / FAIL per check.
4. If any FAIL, rewrite that check's section. Don't ship the original.
5. If all three PASS, ship.
```

For batches (e.g. 50 posts in Postiz, 12 web pages), produce a CSV / table:
- post or page id
- opinion check (PASS/FAIL + one-line reason)
- primitive check (PASS/FAIL + which primitive used or none)
- voice check (PASS/FAIL + voice-gate output)
- verdict (KEEP / EDIT / KILL)

Then Chris signs off the verdicts before any rewrites.

## Anti-patterns this skill exists to catch

- Adopting a popular LinkedIn-thought-leader format (Logan Gott / Justin Welsh / Sahil Bloom carousel templates) just because they "perform". Format is downstream of the gate, not upstream.
- Writing pricing copy that sounds like every other SaaS pricing page.
- Comparison pages that list "TAP vs Competitor X" features without saying what TAP refuses to do that competitor does.
- Cold emails that any music-tech founder could send.
- Threads / X posts that are just trimmed-down LinkedIn maxims.
- AI-generated body copy that has no specific names, dates, campaigns, or numbers.

## Related

- `voice-gate.py` — runtime regex check for HARD/SOFT voice fails, runs daily 07:00 + 22:00
- `social` skill — scheduling pipeline, calls voice-gate before queueing
- `tap-brand-platform-2026.md` — opinion + primitive source-of-truth
- `top-of-mind.md` — the 10x test (parity is failure)
- `feedback_li_image_gotchas.md` — visual carousel format follows this gate, not a fixed template

## Output style

Be terse. For each check, one line: PASS / FAIL + the specific reason. Don't write essays. The point is a fast verdict, not a critique.

Example output:

```
Page: /pricing
- Opinion check:   FAIL — every line could appear under HubSpot or Muck Rack with brand swap.
- Primitive check: FAIL — no TAP-owned term used.
- Voice check:     FAIL — third-person throughout, no first-person founder presence.
Verdict: KILL. Rewrite from scratch around the approval-queue + send-doctrine opinion.
```
