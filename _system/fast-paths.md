---
type: note
date: YYYY-MM-DD
status: processed
llm_context: true
tags: [system, fast-paths, workflows]
---

# Fast-Path Workflows

*Read this at session start (third file, after CONTEXT.md and index.md). Update this file — not the system prompt — when adding new domains or workflow patterns. Log changes in vault-changelog.md.*

*This file ships with example fast-paths. Edit or replace them with workflows that match your life during FIRST_RUN setup.*

---

## Outreach / proposal

Load `Context/CONTEXT.md` + active sprint from `Priorities/priorities.md` → draft immediately. Lead with your most relevant current work. Templates in `My Projects/` if you have them.

---

## Investment idea

Create a note in `Investment Ideas/` using `_system/templates/investment-idea-template.md`. Required fields: ticker, thesis (1 sentence), conviction (high/med/low), source, date. Link to the relevant Synthesis if one exists.

---

## Web clip processing (Ingest protocol)

One source should touch many pages, not produce one extraction:
1. Read the source. Discuss key takeaways if I'm present.
2. Update the relevant `Syntheses/` page — new evidence, revised thesis. Create the page if the topic recurs and lacks one (propose first).
3. Create or update `Mental Models/` and `Investment Ideas/` notes as warranted.
4. Flag contradictions with existing notes.
5. Mark the raw source `status: processed`, `llm_context: false`.
6. Run the post-write checklist.

---

## Log a decision

Trigger: "log a decision", "help me think through [choice]", or any time you're facing a meaningful financial, professional, or personal fork.

**Reference:** [[Syntheses/decision-making]] — full model stack for context.

### Pass 1 — before committing

1. Ask: what's the decision, and what category (financial / professional / personal)? If already described, skip this.
2. Run the **decision classification check**:
   - Is it reversible or irreversible? Consequential or not?
   - If Irreversible + Consequential → full process below. Otherwise → decide fast.
   - Can it be decomposed into smaller reversible experiments?
3. Scaffold the Pass 1 note interactively:
   - **Decision statement** (one sentence — confirm before proceeding)
   - **Root problem** — what would have to be true for this problem not to exist? (separate from solutions)
   - **The Most Important Thing** — if only one criterion could be met, what is it? Add a quantity where possible.
   - **Options** — minimum three. Push for a "third option" beyond the obvious binary. Apply Vanishing Options if stuck: "what would you do if Option A simply didn't exist?"
   - **Criteria** — weighted, with the Most Important Thing ranked first
   - **Timing check** — is this ASAP or ALAP? If ALAP, which signal are you waiting for?
   - **Backcasting** (positive) — project 12 months out, it worked brilliantly. What happened?
   - **Pre-mortem** — project 12 months out, it went badly wrong. What happened? List top 3 failure modes.
   - **Relevant mental models** — link models from the vault relevant to this decision
   - **Tripwires** — if the decision has time-bounded conditions, define at least one tripwire
   - Propose a **review-date**: short-horizon (< 3 months) → 90 days; medium (3–12 months) → 6 months; long-horizon → 12 months
4. Write the note to `Decisions/YYYY-MM-[slug].md` using `_system/templates/decision-template.md` with `decision-type: deliberate`
5. Run post-write checklist: update index.md + log.md; link ≥ 2 related notes

### Pass 2 — closing and reviewing

Trigger: "update decision on [topic]" or "close [decision]".

1. Read the original note
2. Fill the Pass 2 section: outcome, what actually happened vs. what was predicted, which failure modes materialised
3. **Evaluate process, not just outcome** — a good process + bad outcome = bad luck. A bad process + good outcome = dangerous luck. Separate them explicitly.
4. Set `decision-status: closed`
5. Create a `Learnings/` post-mortem if the outcome warrants it; link bidirectionally
6. **Reflect, Learn, Apply, Repeat** — what changes in how you'd approach the next similar decision?

Note: in task-manager.html, closing a `#decision` task via checkbox opens the reasoning modal which auto-creates the vault note. The Pass 2 review still needs to be done in the vault.

---

## Log a retrospective

**Past choices, mistakes, patterns, learnings.**

Trigger: "log a past decision", "write a retrospective on [topic]", "I made a mistake with X", "reflecting on [past choice]", or when the system identifies a pattern worth capturing during monthly evolution or learning recap.

This is NOT a task. No checkbox, no deadline. It's a knowledge artifact.

1. Ask (or infer): what was decided, when, and what happened? Category?
2. Determine quality: **good** (sound call, good process), **mistake** (wrong call or flawed process), **unclear** (outcome still unfolding).
3. Write the note to `Decisions/YYYY-MM-[slug].md` using `_system/templates/retrospective-template.md`:
   - `decision-type: retrospective`
   - `decision-status: closed`
   - `date` = when the original decision was made (not today)
   - `logged-date` = today
   - `quality` = good / mistake / unclear
4. Fill the body: Decision, Context, What Happened, What I Learned, Pattern Tags, Links.
5. Run post-write checklist: update index.md + log.md; link ≥ 2 related notes — especially mental models this decision validates or challenges.

Retrospectives can also be logged directly from the Decisions tab in task-manager.html without needing to create a task first.

**Pattern synthesis:** during monthly evolution review, scan all retrospectives. Surface recurring pattern tags. If 3+ retrospectives share a pattern (e.g. "overconfidence", "acting too early"), propose a `Learnings/` synthesis page that distils the pattern into an actionable mental model update.

---

## Meeting prep

Read the entity page for the person or company (create from `_system/templates/entity-template.md` if missing) → surface relevant Syntheses and Investment Ideas → propose 3 questions. Check `Priorities/priorities.md` for what's active.

---

## Investment strategy / portfolio discussion

Before responding:
1. Fetch current quotes for relevant tickers
2. Surface prices and 52W range inline — do not wait to be asked
3. Flag: 🔴 within 5% of 52W high (extended) · 🟢 down >30% from 52W high (potential value)

**Hard rule:** Never pass position size, cost basis, or P&L to any external API. Ticker symbols only.

---

## Portfolio management / holdings

Read `Portfolio/holdings/` for position data. Price data via ticker symbols only.

---

## Mental model note creation (frontmatter rules)

Whenever creating a mental model note (from web clip, PDF, project chat, or any other path), the frontmatter **must** match this structure exactly:

```yaml
tags:
  - mental-model
  - tag2
related:
  - "[[Note/Path]]"
  - "[[Note/Path2]]"
status: processed
curation: ""
llm_context: true
```

**Non-negotiable rules:**
- `tags` must use block list format (one tag per line with `  -`), never inline `[tag1, tag2]`
- `related` must be a block list of quoted strings `"[[...]]"`, never a bare comma-separated string
- `curation` must always be present, even if empty (`curation: ""`)
- `mental-model` tag must always be included — it powers the Dataview collection queries

**Why:** notes created via project chat bypass Templater, so the template isn't applied automatically. These rules are the manual equivalent of what Templater enforces.

---

## Mental model curation

After a Learning Recap run, you may send curation decisions (e.g. "Mental Model X → Favourite, Mental Model Y → Keep"). Apply them:
- Set `curation: [decision]` in the model's frontmatter
- Log the change in `_system/log.md`
- On next inbox scan: delete any models with `curation: Discard`
