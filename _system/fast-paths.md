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

Load `Context/professional-history.md` + active sprint folder → draft immediately. Lead with your most relevant current work. Templates in `My Projects/` if you have them.

---

## Investment idea

Create a note in `Investment Ideas/` using `_system/templates/investment-idea-template.md`. Required fields: ticker, thesis (1 sentence), conviction (high/med/low), source, date. Link to the relevant Synthesis if one exists.

---

## Web clip processing (Ingest protocol)

One source should touch many pages:
1. Read the source. Discuss key takeaways if I'm present.
2. Update the relevant `Syntheses/` page — new evidence, revised thesis. Create the page if the topic recurs and lacks one (propose first).
3. Create or update `Mental Models/` and `Investment Ideas/` notes as warranted.
4. Flag contradictions with existing notes.
5. Mark the raw source `status: processed`, `llm_context: false`.
6. Run the post-write checklist.

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

## Mental model curation

After a Learning Recap run, you may send curation decisions (e.g. "Mental Model X → Favourite, Mental Model Y → Keep"). Apply them:
- Set `curation: [decision]` in the model's frontmatter
- Log the change in `_system/log.md`
- On next inbox scan: delete any models with `curation: Discard`
