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
│   ├── priorities.md             ← Single editing surface: long-term objectives + all tasks
│   ├── tasks-dashboard.md        ← Live Obsidian Tasks queries: overdue, this week, sprint, upcoming, someday.
│   └── archive/                  ← Dated snapshots
├── Web Clippings/    ← Articles and YouTube captured via Obsidian Web Clipper (llm_context: false always)
├── Syntheses/        ← Living overview pages: topic syntheses + entity pages. Updated on every relevant ingest.
├── Mental Models/    ← Extracted mental models from clips, books, meetings
├── Investment Ideas/ ← Investment theses extracted from research and clips
├── Learnings/        ← Post-mortem analyses of own decisions
├── My Projects/      ← One note or subfolder per project
├── Meeting Notes/    ← Client, internal, personal meetings
├── Notes/            ← General scratchpad
├── Portfolio/        ← PRIVATE. Holdings + trade log. Do not push to GitHub.
├── Books/            ← Processed book notes: summaries, key insights, links to vault concepts
└── _system/          ← Templates, vault-changelog.md, vault-structure.md, system prompt
    ├── index.md      ← Catalog of all wiki notes + Now block. Read at session start; updated on every write
    ├── log.md        ← Append-only operations log
    └── templates/    ← Note templates for each type
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

`llm_context: false` is permanent on all Web Clippings. `status` is the only reliable processing signal:
- `status: inbox` or missing → not yet processed
- `status: processed` → ingest done; a wiki note exists linking back

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

---

## Scheduled tasks

*Add your own scheduled tasks here as you configure them.*

| Task | Schedule | Trigger phrase | Output |
|------|----------|---------------|--------|
| Vault inbox scan | Mondays 10:30 AM | "run inbox scan" | In-place vault edits |
| Priorities & To Do | Mondays 11:00 AM | "run priorities check-in" | `Priorities/weekly-priorities-[W].md` |
| Learning Recap | Mondays 12:30 PM | "run learning recap" | `Learnings/weekly-recap-[W].md` |
| Portfolio price sync | Sundays 8:00 PM | "sync portfolio prices" | Updates `Portfolio/holdings/` frontmatter |
| Monthly evolution | 1st of month 10:00 AM | "run monthly evolution" | In-place vault edits + CONTEXT.md check |
