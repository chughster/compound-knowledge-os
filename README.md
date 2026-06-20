# Compound - A No Code Personal Knowledge OS

Compound is a simple, open source personal knowledge management system built for non-technical people who prefer GUIs over terminal windows. It uses Claude Cowork and Obsidian to record, structure and synthesise your knowledge, goals and life context into an interconnected set of notes that learn from you over time - the content you consume, the decisions you make, the ideas you're tracking.

A Charlie Munger YouTube talk becomes a collection of mental models - surfaced whenever you are facing decisions. A handful of scattered research clips on stocks become a single investment thesis. Your big life goals become actionable tasks in a visual tracker - and when you get stuck, relevant learning and mental models are surfaced to help you get unblocked.

Everything connects. Nothing gets lost. Free on GitHub. Runs on Claude Pro. No code required.

---

## Getting Started

**What you need:**
- [Obsidian](https://obsidian.md/download) - free (Mac, Windows, Linux, iOS, Android)
- [Claude Cowork](https://claude.ai/referral/YU4FcS6hQQ) - Claude Pro desktop app- iCloud - free, for mobile sync

**Setup:**

1. Download the vault: click the green **Code** button on this page, then **Download ZIP**. Unzip the folder to a permanent location on your computer (Documents or iCloud Drive works well). This folder is your Knowledge OS - put it somewhere you'll keep it.

2. Open Obsidian, click **Open folder as vault**, and select the unzipped folder. Your vault is live.

3. Install the required plugins: **Settings - Community Plugins - turn off Restricted Mode - Browse**. Search by name, install, enable.

   | Plugin | Required? |
   |--------|-----------|
   | Tasks | Essential |
   | Dataview | Essential |
   | Templater | Essential |
   | Homepage | Recommended |
   | Git | Optional (for developers) |

   Also install [Obsidian Web Clipper](https://obsidian.md/clipper) - one-click capture from any webpage or YouTube video.

4. Open the **Claude Cowork desktop app**, create a new project, go to **Project Settings**, and paste the contents of `_system/project-instructions.md` into the Custom Instructions field.

5. Open `FIRST_RUN.md` and follow the steps inside. Claude will interview you and configure the whole system for your life in one session.

-> **[Open FIRST_RUN.md](FIRST_RUN.md)**

**The full stack:**

| Tool | Cost | Role |
|------|------|------|
| [Obsidian](https://obsidian.md/download) | Free | Vault, editing, mobile, web clipping |
| [Claude Cowork](https://claude.ai/referral/YU4FcS6hQQ) (desktop app) | Claude Pro | AI reasoning, synthesis, file writing, scheduled tasks |
| iCloud | Free | Mobile sync |
| Obsidian Web Clipper | Free | One-click web capture |
| Obsidian Tasks plugin | Free | Live task dashboard inside Obsidian |
| task-manager.html | Free (included) | App-style task view in any browser |
| Obsidian Dataview plugin | Free | Dynamic vault views |
| Obsidian Templater plugin | Free | Auto-filled note templates |

**Optional paid add-on:**

[Readwise](https://readwise.io) ($9.99/month) syncs your Kindle highlights, book annotations, and reading history directly into a `Readwise/` folder in your vault. Highlights flow in automatically and you process them during ingest sessions. If you prefer free, export Kindle highlights via [Amazon's notebook](https://read.amazon.com/kp/notebook) and paste them manually.

No API keys. No code. No servers.

---

## Why I Built This

Every knowledge system I tried was designed for someone else.

The good ones were built for developers - terminal first, config files, command line setup. The no-code ones were rigid templates that worked fine until my goals changed or my information habits didn't fit the structure. None of them adapted to how I actually think, what I'm actually working on, or the specific way I consume information.

I wanted something that started with me - my context, my quirks, my goals - and got smarter the more I used it. Set it up once. The more you use it, the better it gets.

---

## In Practice

### Example 1: YouTube Video to Mental Models to Action

You watch a long-form interview with a founder or investor. An hour of ideas. Normally you'd retain 10% of it by Friday.

**You clip it.** Obsidian Web Clipper saves the video to your vault, tagged `status: inbox`.

**Claude processes it.** You open a session and say "process this clip." Claude reads the transcript, pulls out 3-5 reusable mental models, and writes each one as a standalone note in `Mental Models/`. Each model gets a plain-language summary, a real-world application, and links to related models already in your vault.

**The Synthesis updates.** If the ideas connect to a topic you're already tracking - decision-making, compounding, whatever - Claude updates the relevant Synthesis page and refines the thesis.

**It lands in your tasks.** If any insight applies to something you're working on, Claude writes a task into your to-do list with a due date. The idea doesn't evaporate.

By Monday's Learning Recap, the video has been distilled into permanent knowledge, cross-linked to your existing thinking, and converted into at least one concrete next step.

---

### Example 2: Research to Investment Thesis to Watchlist

You've been following a sector - nuclear energy, defence, AI infrastructure, whatever. Articles here, a YouTube breakdown there, a podcast mention. The signal is scattered.

**Each piece gets clipped.** Web Clipper saves each one to `Web Clippings/`, tagged `status: inbox`.

**Claude builds the thesis.** You say "process these clips." Claude reads across all of them, finds the common thread, and creates or updates a Synthesis page: a single living page with a current view, evidence for, evidence against, and open questions. Every new clip sharpens it.

**An Investment Idea note gets created.** When the thesis is strong enough, Claude creates a note in `Investment Ideas/` with a ticker, a one-sentence thesis, conviction level, and sources.

**Scheduled monitoring kicks in.** A weekly scheduled task fetches the latest price and market context and appends it to your Investment Idea note automatically. Current context always sits alongside your original thesis.

**The trade becomes a task.** When you decide to act, Claude writes a task into your to-do: buy trigger, price level, rationale. It sits in your dashboard until you execute or cancel. The decision is documented either way.

The full chain - from a YouTube video to a tracked position with documented rationale - happens inside one system, with no separate spreadsheets or bookmarks folders.

---

## How It Works

### Every Session Picks Up Where You Left Off

At the start of every Claude session, three small files load automatically. One tells Claude who you are and what you're working on. One gives it a catalog of your vault. One contains pre-defined workflows for common situations. Claude orients itself in seconds. You start working immediately - no re-explaining, no copy-pasting context.

### You Control What Claude Sees

Every note has a simple on/off flag. Raw web clippings are invisible to Claude until you process them. Processed notes are visible. Your vault can grow to thousands of notes and sessions stay fast and lean - Claude only ever sees what's ready.

### Fast-Path Workflows

Common requests route directly to predefined workflows:

| When you say... | Claude does... |
|-----------------|----------------|
| "process this article" | Reads, updates Synthesis, extracts mental models, marks done |
| "prep me for my meeting with [person]" | Loads entity page, surfaces relevant notes, suggests questions |
| "new investment idea: [ticker]" | Opens template, fills required fields, links to existing research |
| "what are we working on this week" | Reads active priorities, gives ranked weekly focus |

### The Compounding Layer

`Syntheses/` holds one living page per topic. Every relevant ingest updates it.

Ten articles on the same topic become one Synthesis page: current thesis, evidence for, evidence against, open questions, sources. The eleventh article makes it sharper. Knowledge compounds rather than piles up.

### Tasks and Goals

Long-term goals, active sprint, and daily tasks all live in one file. The Obsidian Tasks plugin renders a live dashboard:

| View | What it shows |
|------|--------------|
| Overdue | Missed deadlines |
| Due This Week | What needs to happen now |
| Sprint | Active sprint focus |
| Upcoming | Next 4 weeks |
| Someday | Captured, no date yet |
| Completed | Last 20, most recent first |

When Claude creates a task from an insight, a meeting, or a decision, it writes directly into this file. Tick a checkbox anywhere and the source file updates instantly.

For a full app-style interface, `task-manager.html` opens in any browser. Tasks appear in a clean dark-themed dashboard organised by sprint, due date, and priority. Edit task text, change due dates, update tags - every change writes back directly.

### Automated Maintenance

Scheduled tasks run on a weekly cadence:

| Task | Schedule | Output |
|------|----------|--------|
| Vault inbox scan | Monday 10:30 AM | Processes clippings, cleans orphans, flags stale claims |
| Priorities check-in | Monday 11:00 AM | Weekly priorities note - sprint health, ranked focus |
| Learning recap | Monday 12:30 PM | Weekly recap - deep dives, themes, contradictions, what to explore next |
| Portfolio price sync | Sunday 8:00 PM | Updates holdings with latest prices |
| Monthly evolution | 1st of month | Reviews identity file, flags stale priorities, proposes structural changes |

### Vault Structure

```
Second Brain/
├── Context/          <- Identity files. Claude loads these first.
├── Priorities/       <- Goals, sprint, and all tasks in one file
├── Syntheses/        <- Living thesis pages. The compounding layer.
├── Mental Models/    <- Reusable thinking frameworks
├── Investment Ideas/ <- Theses with ticker, conviction, sources
├── Web Clippings/    <- Raw captures. AI-invisible until processed.
├── Books/            <- Processed book notes
├── Learnings/        <- Post-mortems on your own decisions
├── My Projects/      <- One note or subfolder per project
├── Meeting Notes/    <- Client, work, personal
├── Notes/            <- General scratchpad
└── _system/          <- index, log, structure, fast-paths
```

---

## FAQ

**Does this work on mobile?**

Yes. Obsidian has free apps for iOS and Android. Your vault syncs via iCloud so notes, tasks, and clippings are on your phone. The Obsidian Web Clipper browser extension works on mobile too - clip any article or YouTube video directly into your vault while browsing. AI sessions on mobile use the Claude chat interface. Full file-writing automation is desktop only; mobile gives you the thinking layer wherever you are.

**Does this work on Windows?**

Yes. Obsidian runs on Windows, Mac, and Linux. Claude Cowork is available on both Windows and Mac. One note on sync: iCloud on Windows can be clunky. OneDrive or Dropbox are smoother alternatives if you're on Windows.

**What does it actually cost?**

Obsidian is free. Claude Cowork runs on a Claude Pro subscription. Readwise is optional at $9.99/month. Web Clipper and all Obsidian plugins are free.

**Is my data private?**

Your vault is just files on your computer. Nothing gets uploaded to a cloud service unless you choose to sync it. Claude processes your notes during sessions but does not retain them between conversations.

**Can I use this with other AI tools?**

The vault architecture is not Claude-specific. Theoretically it should work with any agentic AI that can read and write plain files. We haven't tested other setups yet - if you try it, let us know how it goes.

---

*Built by [Sumit Chugh](https://linkedin.com/in/sumitchugh) - founder and independent consultant. I use this system daily to manage research across AI, investing, and venture strategy.*
