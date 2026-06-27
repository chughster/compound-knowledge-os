---
type: note
date: YYYY-MM-DD
status: processed
llm_context: true
tags: [system, vault-structure]
---

# Vault Structure

*Read on demand — when you need the folder map, frontmatter schema, or scheduled tasks registry. Session protocol reads CONTEXT.md + index.md + fast-paths.md at startup; read this file when a task requires structural details. Update this file — not the system prompt — whenever folders are added, removed, or renamed. Log the change in vault-changelog.md.*

---

```
Second Brain/
├── Context/          ← CONTEXT.md and supporting files. Read first.
├── Priorities/       ← Long-term, weekly, and sprint priority tracking
│   ├── priorities.md             ← Single editing surface: long-term objectives + all tasks (with due dates and tags)
│   ├── tasks-dashboard.md        ← Live Obsidian Tasks queries: overdue, this week, sprint, upcoming, someday
│   └── archive/                  ← Dated snapshots
├── Web Clippings/    ← Articles and YouTube captured via Obsidian Web Clipper (llm_context: false always — use status: processed/inbox to track processing state)
├── Syntheses/        ← Living overview pages: topic syntheses + entity pages. The compounding layer — updated on every relevant ingest
├── Mental Models/    ← Extracted mental models from clips, books, meetings
├── Investment Ideas/ ← Investment theses extracted from research and clips
├── Decisions/        ← Prospective decisions (two-pass) and retrospectives (past choices). See fast-paths.md for protocol.
├── Learnings/        ← Post-mortem analyses and weekly/monthly learning recaps
├── My Projects/      ← One note or subfolder per project
├── Meeting Notes/    ← Client, internal, personal meetings
├── Notes/            ← General scratchpad
├── Portfolio/        ← PRIVATE. Holdings + trade log. Do not push to GitHub.
├── Books/            ← Processed book notes: summaries, key insights, links to vault concepts
└── _system/          ← Templates, vault-changelog.md, vault-structure.md, task-specs
    ├── index.md      ← Catalog of all wiki notes + Now block. Read at session start; updated on every write
    ├── log.md        ← Append-only operations log: `## [YYYY-MM-DD] <op> | <title>`
    ├── templates/    ← Note templates for each type
    └── task-specs/   ← Full instructions for each scheduled task. Edit here to change task behaviour.
```

---

## Security rules — Portfolio/

- Never push `Portfolio/` to GitHub or any public repo
- Never pass position size, cost basis, or P&L to any external API
- Ticker symbols only for price lookups

---

## Folder-level exclusions

These folders are always `llm_context: false` regardless of individual note frontmatter:

- `Web Clippings/` — raw captures; treat as excluded until a processed note exists in Mental Models/ or Investment Ideas/

### Web Clippings processing convention

**`llm_context: false` is permanent on all Web Clippings** — it is not a processing signal. Do not use it to determine whether a clip has been processed.

**`status` is the only reliable processing signal:**
- `status: inbox` or missing status → not yet processed
- `status: processed` → ingest is done; a wiki note exists linking back to this clip

When scanning for unprocessed clippings, filter on `status: inbox` (or missing status). Discard any clip with `status: processed` regardless of its `llm_context` value.

---

## Task schema

All tasks live in `Priorities/priorities.md`. Parsed by both Obsidian Tasks plugin and `task-manager.html`.

**Format:** `- [ ] Task text 🎯 N #tag #priority 📅 YYYY-MM-DD`

| Field | Values | Notes |
|-------|--------|-------|
| Horizon | Due date OR `#someday` | Has due date → surfaces in Week/Upcoming tabs by date. No due date → add `#someday` (backlog). Mutually exclusive. |
| Priority | `#p0` / *(default P1)* / `#p2` | P0 = critical; omit for normal; P2 = low urgency |
| Type | `#decision` / `#weekly` | `#decision` = logged decision, lives in Decisions tab, triggers reasoning modal on close. `#weekly` = recurring, shown as a chip. |
| Goal link | `🎯 N` | Links to long-term objective N. task-manager.html groups tasks by this. |
| Done marker | `✅ YYYY-MM-DD` | Set automatically when checkbox ticked |

Note: task-manager.html is date-based — due date is the routing mechanism. `#someday` and `#decision` are suppressed from chip display.

---

## Frontmatter schema

| Field | Applies to | Values / Notes |
|-------|-----------|----------------|
| `type` | all notes | article / youtube / meeting / book / note / project / priority / learning / synthesis / entity / mental-model |
| `source` | all notes | URL or reference string |
| `source_person` | clips, mental models | Author or speaker name |
| `date` | all notes | capture date YYYY-MM-DD |
| `tags` | all notes | topic tags array |
| `project` | project-linked notes | linked project name |
| `status` | all notes | `inbox` / `processed` |
| `llm_context` | all notes | `true` / `false`. Missing = treat as false and flag it |
| `related` | wiki notes | array of `[[wikilinks]]` to related notes |
| `confidence` | Mental Models, Investment Ideas, Syntheses | `high` / `med` / `low` |
| `last-verified` | Syntheses, high-stakes Mental Models | YYYY-MM-DD — flag if >90 days |
| `curation` | Mental Models only | `Favourite` / `Dive Deeper` / `Keep` / `Discard` |
| `ticker` | Investment Ideas | Stock ticker symbol |
| `decision-type` | Decisions | `deliberate` / `retrospective` |
| `decision-status` | Decisions | `open` / `reviewing` / `closed` |
| `quality` | Decisions (retrospective) | `good` / `mistake` / `unclear` |
| `review-date` | Decisions (deliberate) | YYYY-MM-DD — when to run Pass 2 review |

---

## Scheduled tasks

*Add your own scheduled tasks here as you configure them.*

| Task | Schedule | Trigger phrase | Output |
|------|----------|---------------|--------|
| Vault inbox scan | Daily | "run inbox scan" | In-place vault edits |
| Priorities & To Do | Mondays 11:00 AM | "run priorities check-in" | `Priorities/weekly-priorities-[W].md` |
| Learning Recap | Mondays 12:30 PM | "run learning recap" | `Learnings/weekly-recap-[W].md` |
| Monthly evolution | 1st of month 10:00 AM | "run monthly evolution" | In-place vault edits + CONTEXT.md check |

*Full task specs live in `_system/task-specs/`. Edit those files to change task behaviour.*
