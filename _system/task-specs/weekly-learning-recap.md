---
type: note
date: YYYY-MM-DD
status: processed
llm_context: true
tags: [system, scheduled-task, learning-recap]
---

# Task Spec: Weekly Learning Recap

*Full instructions for the weekly-learning-recap scheduled task. Edit this file to change task behaviour.*

**Goal: surface and compound everything learned since the last recap. This is a learning and exploration session — not a productivity session. Let the content lead.**

Read `Context/CONTEXT.md` at the start of each run for current profile. Connect insights to active projects and priorities — only when the connection is genuine.

---

## Step 1: Determine run type and time anchor

Find the most recent existing recap file in `Learnings/` (exclude any `_template` files). Extract its `date:` frontmatter field — this is your **SINCE_DATE** (cutoff; only vault items created/modified after this date are in scope).

If no prior recap file exists, default SINCE_DATE to 7 days ago.

**Output filename logic — never overwrite:**
- If today is Monday: `weekly-recap-[YEAR]-W[WEEK].md`
- Any other day (manual run): `learning-recap-[DATE].md`

Check whether that filename already exists. If it does, append `-run2`, `-run3`, etc. until unique.

## Step 2: Load context

Read:
1. `_system/index.md` — vault catalog for cross-reference lookups
2. `_system/log.md` — scan `ingest` entries since SINCE_DATE

## Step 3: Find captures since last recap

Use bash to find .md files modified since the last recap in:
`Web Clippings/`, `Mental Models/`, `Syntheses/`, `Books/`, `Learnings/`, `Notes/`

Exclude: `.obsidian/`, `archive/`, `_template` files.

If nothing new: output one sentence noting no new captures since SINCE_DATE. Stop.

## Step 4: Read each relevant note

For every file found: check its frontmatter for `llm_context: true` and `status: processed`. Read those fully. Skip notes with `llm_context: false` or `status: inbox`.

## Step 5: Write the learning recap

Write to the output filename determined in Step 1, saved to `Learnings/`.

Use this structure:

```
---
type: note
date: [TODAY as YYYY-MM-DD]
since: [SINCE_DATE as YYYY-MM-DD]
tags: [weekly-learning, learning-recap]
status: processed
llm_context: true
related: []
---

# Weekly Learning Recap — W[N] ([Mon]–[Sun], [YEAR])
# OR for manual runs: # Learning Recap — [DATE] (since [SINCE_DATE])

---

## 1. This Week at a Glance
[One paragraph — how many sources, which domains, dominant voice or medium.]

---

## 2. Insights — Deep Dive
[For each significant insight:]

**[Insight title]**
**[Note Name](source URL)** · Author/Creator

[4–6 sentences. Go past the surface. What is the mechanism? What does it predict? What's non-obvious?]

**Why it matters now:** [1–2 sentences. Connect to active priorities from CONTEXT.md.]

**Connects to:** [1–3 existing vault notes this extends or complicates.]

[Aim for 5–8 insights. Depth over breadth.]

---

## 3. Themes This Week
[2–4 patterns that cut across this week's captures.]

---

## 4. Tensions & Open Questions
[Contradictions with existing vault notes, and the 1–2 most generative open questions this week raised.]

---

## 5. New Mental Models — Curation Table

| Model | Source | Core Concept (1 line) | Suggested Curation |
|-------|--------|----------------------|--------------------|
| **Model Name** | Author | What it says in one sentence | Favourite / Dive Deeper / Keep / Discard |

⚡ Reply with curation decisions and I'll update the vault.

---

## 6. Vault Health

[Lint pass over Syntheses/, Mental Models/, Books/, Learnings/. Check for: stale syntheses (last-verified > 90 days), missing pages (concepts mentioned 3+ times without a dedicated note), orphan notes with no links. Max 5 items.]

---

## 7. What to Read or Watch Next

[3–5 specific recommendations based on this week's themes.]

---

## 8. One Lingering Question

[The single most interesting open question this period's learning raised. One precise sentence.]
```

## Step 6: Housekeeping

1. **Append to `_system/log.md`**: `## [YYYY-MM-DD] ingest | learning recap [filename]` — one-line result.
2. **Update `_system/index.md`** — add the recap file under the Learnings section.
3. If lint identified a missing Synthesis page: flag it with ⚡, do NOT create without approval.

---

**Tone:** Warm but sharp. Curious but grounded. The goal is not to list what was ingested but to understand what was learned. Make it worth reading twice.
