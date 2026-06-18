# Compound — A No Code Personal Knowledge OS

A personal knowledge OS that turns everything you read, watch, and learn into compounding intelligence.

---

## The Problem

**Information overload is getting worse, not better.**

You consume more than ever. News articles, YouTube, Substack, blogs, social media, books. Most of it is genuinely useful. But your brain isn't built to retain, connect, and synthesise across all of it. A framework from a book you read six months ago should inform the decision you're making today. It doesn't — because you have no system linking them.

The content keeps coming. The insight evaporates. You're well-informed. Your thinking doesn't compound.

**Life planning stays shallow without a knowledge layer underneath it.**

You have goals — long-term and short-term. Personal growth, professional growth, financial, health. But goals without a system to track, reflect on, and learn from them are just intentions. Most productivity tools give you lists and calendars. They don't help you think.

What's missing is a layer that connects your goals to what you're learning, surfaces relevant knowledge when you're making decisions, and compounds over time as your thinking evolves.

---

## The Solution

Obsidian stores your knowledge as plain text files. Claude can read plain text files. That's the entire integration — no API, no plugin, no code.

What makes it a *system* is configuration. A single system prompt — included in this repo — tells Claude who you are, how your vault is structured, and what to do in common situations. Every session starts with that context already loaded. No re-explaining. No copy-pasting. Claude picks up exactly where you left off.

**The stack:**

- **Obsidian** (free) — your knowledge lives here. Notes, clippings, tasks, goals. Just files on your computer. Nothing proprietary, nothing that locks you in.
- **Claude Cowork** (~$20/month) — your AI reasoning layer. Reads your vault, writes back to it, runs scheduled maintenance tasks, and handles everything from synthesis to task creation.

**Built for token efficiency — so you get more from every session.** The system loads three small files at session start rather than your entire vault. Raw content stays invisible to Claude until you process it. Maintenance runs on a weekly cadence rather than continuously. Every design decision is optimised to give you maximum value from your Claude subscription.

**Who this is for:**

- You consume a lot of content and retain very little of it
- You want a personal knowledge base but every system you've tried got abandoned
- You want a system that just works — no setup complexity, no command line, no lock-in
- You want AI to do real cognitive work — synthesis, connection, analysis — across everything you know
- You want something that keeps working as your knowledge grows

If you can use Obsidian, you can run this system. [This 15-minute video](https://www.youtube.com/watch?v=z4AbijUCoKU) covers everything you need to get started.

---

## Solution In Action

### Example 1: Podcast → Mental Models → Action

You watch a long-form interview with an investor or founder. An hour of ideas, frameworks, stories. Normally you'd retain 10% of it by Friday.

**You clip it.** Obsidian Web Clipper saves the YouTube video to your vault, tagged `status: inbox`.

**Claude processes it.** You open a session and say "process this clip." Claude reads the transcript, identifies 3–5 reusable mental models, and writes each one as a standalone note in `Mental Models/`. Each model gets a plain-language summary, a real-world application, and links to related models already in your vault.

**The Synthesis updates.** If the ideas connect to a topic you're already tracking — decision-making, compounding, whatever — Claude updates the relevant Synthesis page and refines the thesis.

**It lands in your tasks.** If any insight applies to something you're working on, Claude writes a task into your to-do list with a due date. The idea doesn't evaporate. It becomes something you do.

By Monday's Learning Recap, the clip has been distilled into permanent knowledge, cross-linked to your existing thinking, and converted into at least one concrete next step.

---

### Example 2: News + YouTube → Investment Thesis → Watchlist → Trade

You've been following a sector — nuclear energy, defence, AI infrastructure, whatever it is. Articles here, a YouTube breakdown there, a podcast mention. The signal is scattered.

**Each piece gets clipped.** Web Clipper saves each one to `Web Clippings/`, tagged `status: inbox`.

**Claude builds the thesis.** You say "process these clips." Claude reads across all of them, identifies the common thread, and creates or updates a Synthesis page — a single living page with a current view, evidence for, evidence against, and open questions. Every new clip updates the same page.

**An Investment Idea note gets created.** When the thesis is strong enough, Claude creates a note in `Investment Ideas/` with a ticker, a one-sentence thesis, conviction level, and sources. This is your watchlist.

**Scheduled monitoring kicks in.** A weekly scheduled task fetches the latest price and market context and appends it to your Investment Idea note automatically. Current context always sits alongside your original thesis.

**The trade becomes a task.** When you decide to act, Claude writes a task into your to-do: buy trigger, price level, rationale. It sits in your dashboard until you execute or cancel. The decision is documented either way.

The full chain — from a YouTube video to a tracked position with documented rationale — happens inside one system, with no separate spreadsheets or bookmarks folders.

---

## Getting Started

**What you need:**
- [Obsidian](https://obsidian.md/download) — free download (Mac, Windows, Linux, iOS, Android)
- [Claude Cowork](https://claude.ai) — $20/month desktop app
- iCloud — free, for mobile sync

**Setup:**

1. Download the vault: on this GitHub page, click the green **Code** button → **Download ZIP** → unzip the folder to a permanent location on your computer (e.g. Documents or iCloud Drive). This folder becomes your Knowledge OS — pick somewhere you'll keep it long-term.

2. Open Obsidian → **Open folder as vault** → select the unzipped folder. Your vault is now live.

3. Install the required Obsidian plugins: **Settings → Community Plugins → turn off Restricted Mode → Browse**. Search by name, install, enable.

   | Plugin | Required? |
   |--------|-----------|
   | Tasks | Essential |
   | Dataview | Essential |
   | Templater | Essential |
   | Homepage | Recommended |
   | Git | Optional (for developers) |

   Also install the [Obsidian Web Clipper](https://obsidian.md/clipper) browser extension — one-click capture from any web page or YouTube video.

4. Open the **Claude Cowork desktop app** → create a new project → open **Project Settings** → paste the contents of `_system/project-instructions.md` into the Custom Instructions field.

5. Open `FIRST_RUN.md` and follow the steps inside.

→ **[Open FIRST_RUN.md](FIRST_RUN.md)**

**Stack:**

| Tool | Cost | Role |
|------|------|------|
| [Obsidian](https://obsidian.md/download) | Free | Vault, editing, mobile, web clipping |
| [Claude Cowork](https://claude.ai/download) (desktop app) | $20/month | AI reasoning, synthesis, file writing, scheduled tasks |
| iCloud | Free | Mobile sync |
| Obsidian Web Clipper | Free | One-click web capture |
| Obsidian Tasks plugin | Free | Live task dashboard inside Obsidian |
| task-manager.html | Free (included) | App-style task view in any browser |
| Obsidian Dataview plugin | Free | Dynamic vault views |
| Obsidian Templater plugin | Free | Auto-filled note templates |

**Optional paid add-on:**

[Readwise](https://readwise.io) ($9.99/month billed annually) syncs your Kindle highlights, book annotations, and reading history directly into a `Readwise/` folder in your vault. Claude treats this folder as raw input — highlights flow in automatically, and you process them into permanent knowledge during ingest sessions. If you prefer free alternatives, export your Kindle highlights via [Kindle's highlight export](https://read.amazon.com/kp/notebook) or use [Goodreads export](https://www.goodreads.com/review/import) and paste them manually.

No API keys. No code. No servers.

---

## How It Works

### Session Start

Three files load at the start of every Claude session:

```
1. Context/CONTEXT.md        ← Who you are, what you're working on, how you think
2. _system/index.md          ← Catalog of all notes + what's active right now
3. _system/fast-paths.md     ← Pre-defined workflows for common situations
```

Identity → orientation → operating procedures. Typically under 3,000 tokens. Claude orients itself in seconds. You start working immediately.

### You Control What AI Sees

Every note has a simple flag in its YAML header:

```yaml
llm_context: true    # Claude can read and reference this note
llm_context: false   # Claude ignores this note
```

Raw web clippings are always `false`. Processed wiki notes are `true`. Your vault can grow to thousands of notes — Claude only ever sees what's been processed and marked ready. This keeps sessions lean and every token working harder for you.

### Fast-Path Workflows

`fast-paths.md` routes common requests directly to predefined workflows — no ambiguity, no re-explaining:

| When you say... | Claude does... |
|-----------------|----------------|
| "process this article" | Reads → updates Synthesis → extracts mental models → marks done |
| "prep me for my meeting with [person]" | Loads entity page → surfaces relevant notes → suggests questions |
| "new investment idea: [ticker]" | Opens template → fills required fields → links to existing research |
| "what are we working on this week" | Reads active priorities → gives ranked weekly focus |

### The Compounding Layer

`Syntheses/` holds one living page per topic. Every relevant ingest updates it.

Ten articles on the same topic → one Synthesis page with a current thesis, evidence for, evidence against, open questions, and sources. The eleventh article makes it sharper. Your knowledge compounds rather than piles up.

### Tasks and Goals

Long-term goals, active sprint, and daily tasks all live in `Priorities/priorities.md`. The Obsidian Tasks plugin renders a live dashboard:

| View | What it shows |
|------|--------------|
| 🚨 Overdue | Missed deadlines |
| 📅 Due This Week | What needs to happen now |
| 🔥 Sprint | Active sprint focus |
| 🗓️ Upcoming | Next 4 weeks |
| 🌀 Someday | Captured, no date yet |
| ✅ Completed | Last 20, most recent first |

When Claude creates a task from an insight, a meeting, or a trade decision — it writes directly into this same file. Tick a checkbox anywhere and the source file updates instantly.

For a full app-style interface, `task-manager.html` opens in any browser. Tell Claude your goal, refine in chat, and the tasks appear in a clean dark-themed dashboard — organised by sprint, due date, and priority, ready to strike off like in Todoist or AnyDo. Edit task text, change due dates, update tags — every change writes back to `priorities.md` directly.

### Automated Maintenance

Scheduled tasks run in the background on a weekly cadence:

| Task | Schedule | Output |
|------|----------|--------|
| Vault inbox scan | Monday 10:30 AM | Processes clippings, cleans orphans, flags stale claims |
| Priorities check-in | Monday 11:00 AM | Weekly priorities note — sprint health, ranked focus |
| Learning recap | Monday 12:30 PM | Weekly recap — deep dives, themes, contradictions, what to explore next |
| Portfolio price sync | Sunday 8:00 PM | Updates holdings with latest prices |
| Monthly evolution | 1st of month | Reviews identity file, flags stale priorities, proposes structural changes |

### Vault Structure

```
Second Brain/
├── Context/          ← Identity files. Claude loads these first.
├── Priorities/       ← Goals, sprint, and all tasks in one file
├── Syntheses/        ← Living thesis pages. The compounding layer.
├── Mental Models/    ← Reusable thinking frameworks
├── Investment Ideas/ ← Theses with ticker, conviction, sources
├── Web Clippings/    ← Raw captures. AI-invisible until processed.
├── Books/            ← Processed book notes
├── Learnings/        ← Post-mortems on your own decisions
├── My Projects/      ← One note or subfolder per project
├── Meeting Notes/    ← Client, work, personal
├── Notes/            ← General scratchpad
└── _system/          ← index, log, structure, fast-paths
```

---

## FAQ

**Does this work on mobile?**

Yes. Obsidian has free apps for iOS and Android. Your vault syncs via iCloud so notes, tasks, and clippings are available on your phone. The Obsidian Web Clipper browser extension works on mobile too — clip any article or YouTube video directly into your vault while browsing. For AI sessions on the go, Claude Cowork works through the Claude chat interface on mobile — you can process content, ask questions, and work with your vault through conversation. Full file-writing automation works on desktop via the Cowork app; mobile gives you the thinking layer wherever you are.

**Does this work on Windows?**

Yes. Obsidian runs on Windows, Mac, and Linux. Claude Cowork is available on both Windows and Mac. One note on sync: iCloud on Windows works but can be clunky. If you're on Windows, OneDrive or Dropbox are smoother alternatives for keeping your vault accessible across devices.

**What does it actually cost?**

Obsidian is free. Claude Cowork is $20/month (Claude Pro). Readwise is optional at $9.99/month. Web Clipper and all Obsidian plugins are free. Total minimum: $20/month.

**Is my data private?**

Your vault is just files on your computer — nothing is uploaded to a cloud service unless you choose to sync it. Claude processes your notes during sessions but does not retain them between conversations.

**Can I use this without Claude Cowork?**

Yes, with one limitation. Claude.ai on the web handles all the thinking and synthesis. The only difference is file writing — Cowork writes files directly to your vault; on the web, Claude generates the content and you paste it manually. For daily use with scheduled tasks and automated maintenance, Cowork is significantly smoother.

Theoretically, this system should work with other agentic AI harnesses that can read and write plain files — the vault architecture is not Claude-specific. We haven't tested other setups yet and that's on the roadmap. If you try it with another system, let us know how it goes.

---

*Built by [Sumit Chugh](https://linkedin.com/in/sumitchugh) — founder and independent consultant. I use this system daily to manage research across AI, investing, and venture strategy.*
