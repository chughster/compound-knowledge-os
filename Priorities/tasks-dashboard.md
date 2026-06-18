---
type: note
date: YYYY-MM-DD
status: processed
llm_context: true
tags: [system, tasks, dashboard]
---

# Tasks Dashboard

*Live view of all tasks in `priorities.md`. Tick any checkbox here — it updates the source file automatically.*

---

## 🚨 Overdue

```tasks
not done
due before today
path includes Priorities
```

---

## 📅 Due This Week

```tasks
not done
due this week
path includes Priorities
sort by due
```

---

## 🔥 Sprint

```tasks
not done
tag includes #sprint
path includes Priorities
sort by due
```

---

## 🗓️ Upcoming (next 4 weeks)

```tasks
not done
due after today
due before in 4 weeks
tags do not include #sprint
path includes Priorities
sort by due
```

---

## 🌀 Someday / No Date

```tasks
not done
no due date
tags do not include #sprint
path includes Priorities
```

---

## ✅ Completed

```tasks
done
path includes Priorities
sort by done reverse
limit 20
```
