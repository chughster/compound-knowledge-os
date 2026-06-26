---
type: note
date: YYYY-MM-DD
status: processed
llm_context: true
tags: [system, scheduled-task, web-clippings]
---

# Task Spec: Process Web Clippings

*Full instructions for the process-web-clippings scheduled task. Edit this file to change task behaviour.*

Read `_system/vault-structure.md` for current folder map, exclusion rules, and frontmatter schema before processing any clip.

---

## Step 0 — Fast pre-check

Use bash to find all .md files in `Web Clippings/` where:
- `status: inbox` or `status: "inbox"` is in the frontmatter, OR
- No `status:` field exists at all

If both checks return nothing: output "No unprocessed web clippings." and stop.

---

## Step 1 — Process each clip

For each file identified in Step 0, read its content. Then decide:
- Contains useful mental models, frameworks, or decision-making principles? → write a note per model to `Mental Models/`
- Mentions specific companies, stocks, or investable assets worth tracking? → write a note to `Investment Ideas/`
- A clip may yield both types.

Before writing any note, check if it already exists (similar name in the target folder, or matching source URL in frontmatter). Skip if duplicate.

### Mental Model format

Filename: `[Model Name].md` (short, punchy, title-case)

```
---
type: mental-model
source: "[URL from clip]"
source_person: [Author/Speaker name if known]
date: [today's date YYYY-MM-DD]
tags:
  - mental-model
  - [2–4 relevant topic tags]
related: []
status: processed
confidence: [high/med/low]
curation: ""
llm_context: true
---

# [Model Name]

## Core concept
[2–4 sentences. What is the insight? Make it generalisable.]

## Examples from source
[Bullet list of concrete examples from the clip.]

## How to apply
[How should you use this? Connect to active projects and priorities from CONTEXT.md.]

## Related models
[Wikilinks to existing vault notes. Minimum 2 where they exist.]
```

### Investment Idea format

Filename: `[Company Name].md`

```
---
type: investment-idea
date: [today's date YYYY-MM-DD]
company: [Company name]
ticker: [TICKER if public, omit if private]
source_person: [Author/Speaker if known]
source_url: "[URL from clip]"
status: watching
tags:
  - investment-idea
  - [2–4 relevant tags]
related: []
confidence: [high/med/low]
llm_context: true
---

# [Company Name]

## Thesis
[1–3 sentences: why is this interesting as an investment?]

## Source
**Person:** [if known]  **Published:** [date]  **URL:** [url]

## Key points from source
[Bullet list of the most relevant claims and data points.]

## Moat / edge
[Structural advantage.]

## Risks
[Key risks — honest, not promotional.]

## Status
`watching` — [What would move this to active research or a buy?]
```

---

## Step 2 — Update Syntheses

Check `Syntheses/` for pages relevant to each clip. If one exists: add new evidence (cite via [[link]]), revise Current view if warranted, update `last-verified`. If a new claim contradicts an existing claim: do not overwrite — flag both in your summary for adjudication. If a topic recurs across 3+ notes with no synthesis page: propose one in summary, do not create without approval.

---

## Step 3 — Mark clip as processed

Update the original clip's frontmatter:
- `status: processed`
- `llm_context: false`
- `processed_into: ["Note1.md", "Note2.md"]` (list of created notes)

---

## Step 4 — Post-write checklist

1. Update `_system/index.md` — add one line per new note under the correct folder section; revise lines for updated syntheses.
2. Append to `_system/log.md`: `## [YYYY-MM-DD] ingest | [clip titles]` with 1–2 line note of what was created/updated.

---

## Step 5 — Summary

Output under 150 words: clips processed, notes created, syntheses updated, contradictions flagged, proposals made, anything skipped and why.
