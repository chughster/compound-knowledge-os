---
type: note
date: YYYY-MM-DD
status: processed
llm_context: true
tags: [system, scheduled-task, weekly-review]
---

# Task Spec: Weekly Review

*Full instructions for the weekly-review scheduled task. Edit this file to change task behaviour.*

**Goal: accountability and forward motion. This is a productivity session, not a learning session. Do not surface insights or explore ideas — that runs separately at 12:30 PM.**

---

## Step 1: Load context

Read these files in order:
1. `Context/CONTEXT.md`
2. `Priorities/priorities.md`
3. `_system/index.md`
4. `_system/log.md` — last 2 weeks of entries only

## Step 2: Find completed tasks and task activity this week

From priorities.md: collect all `- [x]` items (completed tasks).
Identify what was built, decided, or ingested since last Monday from the log.
Calculate days remaining to any active sprint deadline from today's date.

## Step 3: Write the check-in file

Determine the current ISO week number using bash: `date +%V`
Date range: current Monday to Sunday.

Write to: `Priorities/weekly-priorities-[YEAR]-W[ISO_WEEK].md`

Use this structure:

```
---
type: note
date: [TODAY as YYYY-MM-DD]
tags: [weekly-priorities, productivity, tasks]
status: processed
llm_context: true
related: [[priorities]]
---

# Weekly Priorities — W[N] ([Mon date]–[Sun date], [YEAR])

*Automated run.*

---

## 1. Sprint Health

**[Sprint name] — [X] days to [deadline date]**

[Traffic light]: 🟢 On track | 🟡 In motion but slow | 🟠 Stalled | 🔴 At risk

[2–3 sentences. What is moving. What is stuck. The single biggest risk to hitting the deadline.]

---

## 2. Completed This Week

[List all completed items since last Monday with completion dates. If nothing: state it directly.]

---

## 3. Overdue & Slipping

[Every task with a past due date that is not complete. Task name · due date · days overdue · one-sentence read. If none: one line.]

---

## 4. This Week's Priority Order

The 5 tasks that will move the needle most this week, ranked.

| # | Task | Due | Why it's #[N] |
|---|------|-----|----------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |

---

## 5. Full Task Board — Next 14 Days

All open tasks due in the next 14 days from priorities.md.

| Task | Due | 🔴/🟡 |
|------|-----|-------|

🔴 = due this week | 🟡 = due next week

---

## 6. Long-term Priority Status

| Priority | Status | Signal |
|----------|--------|--------|
| [from priorities.md] | 🟢/🟡/🟠/🔴/⚪ | One sentence |

---

## 7. Pattern Call-Out

[2–3 items max. Look at the last 3–4 weeks of log entries and completed/overdue tasks. Call out any recurring pattern directly: repeated deferrals, time spent on non-sprint work, avoidance of a category. Specific, not vague.]

---

## ⚡ Open Items

[Specific approvals, task clarifications, or structural changes needed.]
```

---

## Step 4: Housekeeping

1. **Update `_system/index.md` Now block** — refresh active sprint, this week's top 5 (with due dates). Keep it to 3 bullet lines max.
2. **Append to `_system/log.md`**: `## [YYYY-MM-DD] decide | weekly priorities W[N]` — one-line result.
3. **Archive previous week's check-in**: copy `Priorities/weekly-priorities-[YEAR]-W[N-1].md` → `Priorities/archive/[YEAR]-W[N-1]-priorities.md`. Skip if no previous file.
4. **Update index.md** to reflect the new check-in file under Priorities section.

---

**Tone:** Direct. Short sentences. No filler. This check-in should be uncomfortable if things are slipping — that friction is the point.

**This is not the only Monday scheduled task.** The vault inbox scan runs earlier. The learning recap runs at 12:30 PM. Keep this focused entirely on productivity and task accountability.
