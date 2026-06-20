# Compound - A No Code Personal Knowledge OS

Compound is a simple, open source personal knowledge management system built for people who prefer GUIs over terminal windows. It uses Claude Cowork and Obsidian to record, structure and synthesise your knowledge, goals and life context into an interconnected set of notes that learn from you over time.

---

## In Practice

**A YouTube talk becomes a mental model library.**
You watch a Charlie Munger lecture. You clip it. The system processes it automatically - extracts the key mental models, files them into your vault, and links them to related ideas already there. Next time you're facing a decision, the relevant models surface on their own.

**Scattered research becomes a single investment thesis.**
You clip articles, YouTube breakdowns, and podcast snippets on a sector as you find them. The system processes each one automatically - building and sharpening a single living page with a current thesis, evidence for, evidence against, and open questions.

**Big life goals become a working task system.**
You tell Claude your goals. It breaks them into a prioritised task list in a visual tracker. When you get stuck, it surfaces the learning and mental models most relevant to unblocking you.

**Your weekly learning recaps itself.**
Every Monday, Claude scans your vault, surfaces what you've been learning, flags contradictions, and suggests what to explore next. Your thinking compounds whether or not you're paying attention.

---

## Why I Built This

Every knowledge system I tried was designed for someone else.

The good ones were built for developers - terminal first, config files, command line setup. The no-code ones were rigid templates that worked fine until my goals changed or my information habits didn't fit the structure. None of them adapted to how I actually think, what I'm actually working on, or the specific way I consume information.

I wanted something that started with me - my context, my quirks, my goals - and got smarter the more I used it. Set it up once. The more you use it, the better it gets.

---

## Getting Started

**What you need:**
- [Obsidian](https://obsidian.md/download) - a free note-taking app that works brilliantly with Claude and markdown files (Mac, Windows, Linux, iOS, Android)
- [Claude Cowork](https://claude.ai/referral/YU4FcS6hQQ) - Claude Pro desktop app
- iCloud - free, optional (only needed if you want mobile sync)

No API keys. No code. No servers.

**Setup:**

1. Download the vault: click the green **Code** button on this page, then **Download ZIP**. Unzip the folder to a permanent location on your computer (Documents or iCloud Drive works well).

2. Open Obsidian, click **Open folder as vault**, and select the unzipped folder. Your vault is live.

3. Install the required plugins: **Settings - Community Plugins - turn off Restricted Mode - Browse**. Search by name, install, enable.

   | Plugin | Required? |
   |--------|-----------|
   | Tasks | Essential |
   | Dataview | Essential |
   | Templater | Essential |
   | Homepage | Recommended |

   Also install [Obsidian Web Clipper](https://obsidian.md/clipper) - one-click capture from any webpage or YouTube video.

4. Open the **Claude Cowork desktop app**, create a new project. In Obsidian, open `_system/project-instructions.md`, copy the full contents, and paste into the **Custom Instructions** field in Cowork. Save.

5. Open `FIRST_RUN.md` and follow the steps inside. Claude will interview you and configure the whole system for your life in one session.

-> **[Open FIRST_RUN.md](FIRST_RUN.md)**

**Optional paid add-on:**

[Readwise](https://readwise.io) ($9.99/month) syncs your Kindle highlights and book annotations directly into your vault. If you prefer free, export Kindle highlights via [Amazon's notebook](https://read.amazon.com/kp/notebook) and paste them manually.

---

## How It Works

### Every Session Picks Up Where You Left Off

At the start of every Claude session, three small files load automatically. One tells Claude who you are and what you're working on. One gives it a catalog of your vault. One contains pre-defined workflows for common situations. Claude orients itself in seconds - no re-explaining, no copy-pasting context.

### You Control What Claude Sees

Every note has a simple on/off flag. Raw web clippings are invisible to Claude until you process them. Processed notes are visible. Your vault can grow to thousands of notes and sessions stay fast - Claude only ever sees what's ready.

### Fast-Path Workflows

Common requests route directly to predefined workflows:

| When you say... | Claude does... |
|-----------------|----------------|
| "process this article" | Reads, updates Synthesis, extracts mental models, marks done |
| "prep me for my meeting with [person]" | Loads entity page, surfaces relevant notes, suggests questions |
| "new investment idea: [ticker]" | Opens template, fills required fields, links to existing research |
| "what are we working on this week" | Reads active priorities, gives ranked weekly focus |

### The Compounding Layer

One living page per topic. Every relevant piece of content you process updates it. Ten articles on the same topic become one sharp page. The eleventh makes it sharper. Knowledge compounds rather than piles up.

### Tasks and Goals

Goals, sprint, and daily tasks all live in one file. The Obsidian Tasks plugin renders a live dashboard - overdue, this week, sprint, upcoming, someday. When Claude creates a task from an insight or a decision, it writes directly into this file. For a full app-style view, `task-manager.html` opens in any browser.

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

Yes. Obsidian has free apps for iOS and Android. Your vault syncs via iCloud so notes, tasks, and clippings are on your phone. The Obsidian Web Clipper works on mobile too - clip any article or YouTube video directly into your vault while browsing. Full file-writing automation is desktop only; mobile gives you the thinking layer wherever you are.

**Does this work on Windows?**

Yes. Obsidian runs on Windows, Mac, and Linux. Claude Cowork is available on both. One note on sync: iCloud on Windows can be clunky. OneDrive or Dropbox are smoother alternatives.

**What does it actually cost?**

Obsidian is free. Claude Cowork runs on a Claude Pro subscription. Readwise is optional at $9.99/month. Web Clipper and all Obsidian plugins are free.

**Is my data private?**

Your vault is just files on your computer. Nothing gets uploaded to a cloud service unless you choose to sync it. Claude processes your notes during sessions but does not retain them between conversations.

**Can I use this with other AI tools?**

The vault architecture is not Claude-specific. Theoretically it should work with any agentic AI that can read and write plain files. We haven't tested other setups yet - if you try it, let us know how it goes.

**If you can use Obsidian, you can run this.** [This 15-minute video](https://www.youtube.com/watch?v=z4AbijUCoKU) covers everything you need to get started with Obsidian.

---

*Built by [Sumit Chugh](https://linkedin.com/in/sumitchugh) - founder and independent consultant. I use this system daily to manage research across AI, investing, and venture strategy.*
