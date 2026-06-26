---
type: note
date: YYYY-MM-DD
status: processed
llm_context: true
tags: [system, scheduled-task, monthly-review]
---

# Task Spec: Monthly Evolution Review

*Full instructions for the monthly-evolution-review scheduled task. Edit this file to change task behaviour.*

It's the 1st of the month — time for the monthly evolution review.

Start by reading:
1. `Context/CONTEXT.md`
2. `Priorities/priorities.md`
3. `_system/vault-changelog.md`
4. `_system/log.md` — last 30 days of entries

Then run each step in order. Present one suggestion at a time. Wait for approval or rejection before moving to the next.

---

**Step 1 — Changelog review**
Summarise structural changes made to the vault last month. Flag anything approved but not fully implemented.

**Step 2 — Long-term priorities check**
Review the long-term objectives in priorities.md. Are these still the right objectives? Flag anything stale, resolved, or missing given the past month's activity. Propose specific edits — wait for confirmation before writing.

**Step 3 — Fastest-growing areas**
Identify the three folders with the most new notes in the last 30 days. What does this tell us about where attention is going?

**Step 4 — Dormant areas**
Identify any folders or sections with no new notes in 30 days. Are these intentionally quiet or neglected?

**Step 5 — System health check**
1. **Index size** — report line count of `_system/index.md`. If it exceeds ~600 lines, propose splitting it per folder — token cost at session start is the concern.
2. **Index accuracy spot-check** — sample 10 random index lines; verify the files exist and summaries still match. Report accuracy.
3. **Syntheses health** — for each page in Syntheses/: is it being updated, is `last-verified` current, is the Current view consistent with recent ingests? Flag dead syntheses (no updates in 60+ days) for archive or revival.
4. **Log volume** — if log.md exceeds ~500 entries, propose archiving entries older than 6 months to `_system/log-archive.md`.
5. **Task-spec freshness** — review each file in `_system/task-specs/`. Flag any spec that references hardcoded year strings, outdated sprint names, or paths that no longer exist.

**Step 6 — Mental model collection audit**
Read all notes in `Mental Models/` where `llm_context: true`. Then:

1. **Favourites check** — are the Favourite-tagged models ones you actively reach for? Flag any that haven't appeared in decisions or key learnings over the past month.
2. **Retirement candidates** — identify models that are: redundant (fully embedded in another model), situationally irrelevant (don't apply to your current life/work), or unused in recent decisions. For each: state which model, why you're flagging it, and what (if anything) it would be replaced by.
3. **Gaps** — based on the past month's activity, is there a mental model that should exist but doesn't? Describe the gap in one sentence. Do not create the note — just flag it.

Present as a short table. Wait for approval before making any changes. When approved: set `curation: Discard` on retirement candidates (auto-deleted on next inbox scan). Log all changes to vault-changelog.md.

**Step 7 — Decision journal review**
1. Read all notes in `Decisions/` where `decision-status: open` or `reviewing`.
2. For each note where `review-date` is today or past: flag it — "This decision is due for a Pass 2 review." Include the decision title, original choice, and expected outcome.
3. For each note where `review-date` is within the next 30 days: mention it as coming up soon.
4. If you want to close a decision in this session: fill the Pass 2 section, set `decision-status: closed`, propose a Learnings/ post-mortem if significant. Link both notes bidirectionally.

**Step 8 — Tripwire audit**
1. Read all open decisions in `Decisions/`.
2. For each: scan the body for Tripwires — time-bounded conditions or signals defined in the decision.
3. Check whether any conditions have been met based on today's date and available context. If a condition is time-based and the date has passed, flag it.
4. Report: each open decision with its tripwires, status (fired / pending / unable to verify), and recommended action.

**Step 9 — Structure suggestion**
Propose one structural improvement based on usage patterns — a new folder, a tag convention, a merge, or a split. One suggestion only. Wait for approval before logging or acting.

**Step 10 — CONTEXT.md update**
Review CONTEXT.md. Suggest meaningful updates based on the past month — changed priorities, new projects, resolved situations. Propose the exact edits — wait for confirmation before writing.

---

After the review: append to `_system/log.md`: `## [YYYY-MM-DD] lint | monthly evolution` with a 1-line result.

Rules:
- Never make file changes without explicit approval
- Log every approved change to `_system/vault-changelog.md`
- Tone: direct, sharp, no filler. Short sentences.
