# Compound - Open Source Personal Knowledge OS

People are consuming more information than ever. Very little of it compounds into better decisions.

Compound is a free, open-source Personal Knowledge OS built on Obsidian and Claude Cowork. It transforms everything you read, watch, learn, and decide into a connected intelligence layer that grows more valuable over time.

No API keys. No code. No terminal.

---

## In Practice

**A YouTube talk becomes a mental model library.**
You watch a Charlie Munger lecture. You clip it. The system processes it automatically - extracts the key mental models, files them into your vault, and links them to related ideas already there. Next time you're facing a decision, the relevant models surface on their own.

**Scattered research becomes a single living thesis.**
You clip articles, YouTube breakdowns, and podcast snippets on a sector as you find them. The system processes each one - building and sharpening a single page with a current thesis, evidence for, evidence against, and open questions. The eleventh article makes it sharper than the tenth.

**Hard decisions become documented reasoning.**
When you face a decision, tell Claude. It runs a structured framework: classifies the decision type, finds the real underlying problem, forces a third option, runs a pre-mortem. You set tripwires. Six months later, the system surfaces the note and asks: was the process sound?

**Big life goals become a working task system.**
You tell Claude your goals. It breaks them into a prioritised task list tracked against a sprint. When you get stuck, it surfaces the learning and mental models most relevant to unblocking you. Every Monday, the system reviews what's complete and tells you what to focus on next.

---

## Getting Started

**Option 1 - Install with Claude Cowork (recommended)**

Have Claude handle the download, setup, and first-run configuration automatically.

1. Install [Obsidian](https://obsidian.md/download) and [Claude Cowork](https://claude.ai/referral/YU4FcS6hQQ) if you haven't already
2. Open Claude Cowork and create a new project (top left, + New Project)
3. Open [AGENT_SETUP.md](AGENT_SETUP.md), copy the prompt, and paste it into the chat of that new project
4. Claude will request access to Terminal and Obsidian during installation — approve both when prompted
5. Claude downloads and installs the vault, then guides you through 3 short manual steps: open the vault in Obsidian, enable plugins, and paste the project instructions into Cowork
6. Claude runs the first-run interview and configures the system for your life

---

**Option 2 - Manual install**

**What you need:**
- [Obsidian](https://obsidian.md/download) - a free note-taking app (Mac, Windows, Linux, iOS, Android)
- [Claude Cowork](https://claude.ai/referral/YU4FcS6hQQ) - Claude Pro desktop app
- iCloud - optional, only needed for mobile sync

**Setup:**

1. Download the vault: click the green **Code** button on this page, then **Download ZIP**. Unzip to a permanent location on your computer.

2. Open Obsidian, click **Open folder as vault**, and select the unzipped folder.

3. In Obsidian, go to **Settings - Community Plugins** and turn off Restricted Mode. Obsidian will ask you to confirm - accept. The 4 required plugins (Tasks, Dataview, Templater, Homepage) are pre-installed and will enable automatically.

   Also install [Obsidian Web Clipper](https://obsidian.md/clipper) - one-click capture from any webpage or YouTube video.

4. Open the **Claude Cowork desktop app** and create a new project. Open `_system/project-instructions.md` from your vault folder in any text editor, copy the full contents, and paste into the **Instructions** field in Cowork. Save.

5. Open `FIRST_RUN.md` and follow the steps. Claude interviews you and configures the whole system for your life in one session.

**[Open FIRST_RUN.md to begin →](FIRST_RUN.md)**

**Optional:** [Readwise](https://readwise.io) (paid, check current pricing) syncs Kindle highlights directly into your vault. Free alternative: export via [Amazon's notebook](https://read.amazon.com/kp/notebook) and paste manually.

---

## How It Works

Compound works across three layers:

**Think** - knowledge captured and connected so the right ideas surface when you need them.
**Decide** - a structured framework for making decisions and learning from them over time.
**Do** - goals, sprints, and weekly reviews that keep you moving forward.

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
| "what are we working on this week" | Reads active priorities, gives ranked weekly focus |
| "help me think through [decision]" | Runs structured decision framework, writes note to vault |

### The Compounding Layer

One living page per topic. Every relevant piece of content you process updates it. Ten articles on the same topic become one sharp page. The eleventh makes it sharper. Knowledge compounds rather than piles up.

### Tasks and Goals

Goals, sprint, and daily tasks all live in one file. The Obsidian Tasks plugin renders a live dashboard - overdue, this week, sprint, upcoming, someday. When Claude creates a task from an insight or a decision, it writes directly into this file. For a full app-style view, `task-manager.html` opens in any browser.

### Vault Structure

```
Compound Vault/
├── Context/          <- Identity files. Claude loads these first.
├── Priorities/       <- Goals, sprint, and all tasks in one file
├── Syntheses/        <- Living thesis pages. The compounding layer.
├── Mental Models/    <- Reusable thinking frameworks
├── Decisions/        <- Documented reasoning and retrospectives
├── Investment Ideas/ <- Theses with ticker, conviction, sources
├── Web Clippings/    <- Raw captures. AI-invisible until processed.
├── Books/            <- Processed book notes
├── Learnings/        <- Weekly recaps and post-mortems
├── My Projects/      <- One note or subfolder per project
├── Meeting Notes/    <- Client, work, personal
├── Notes/            <- General scratchpad
└── _system/          <- index, log, structure, fast-paths
```

---

## FAQ

**Does this work on mobile?**
Yes. Obsidian has free iOS and Android apps. Your vault syncs via iCloud, OneDrive, or Dropbox so notes, tasks, and clippings are on your phone. The Web Clipper works on mobile too. Full automation is desktop only; mobile gives you the thinking layer wherever you are.

**Does this work on Windows?**
Yes. Obsidian runs on Windows, Mac, and Linux. Claude Cowork is available on Mac and Windows. iCloud on Windows can be clunky - OneDrive or Dropbox are smoother alternatives.

**What does it actually cost?**
Obsidian is free. Claude Cowork runs on a Claude Pro subscription. Readwise is optional (check current pricing at readwise.io). Web Clipper and all Obsidian plugins are free.

**Is my data private?**
Your vault files live on your computer. Claude processes your notes during sessions per Anthropic's standard terms for your plan. Check your plan's data usage policy if this matters to you. Nothing is uploaded to any third-party service.

**Do I need to know Obsidian?**
Optional. Setup requires no Obsidian knowledge. Just open the vault and the plugins load themselves. To get full value from the system, it's worth getting acquainted with the basics. [This 15-minute video](https://www.youtube.com/watch?v=z4AbijUCoKU) covers everything you need.

---

## Why I Built This

Every knowledge system I tried was designed for someone else.

The good ones were built for developers - terminal first, config files, command line setup. The no-code ones were rigid templates that worked fine until my goals changed or my information habits didn't fit the structure. None of them adapted to how I actually think, what I'm actually working on, or the specific way I consume information.

And none of them helped me make better decisions with what I'd learned.

I wanted something that started with me - my context, my quirks, my goals - and evolved with my usage to make me sharper and more productive over time.

---

*Built by [Sumit Chugh](https://linkedin.com/in/sumitchugh) - founder and independent consultant. I use this system daily to manage research across AI, investing, and venture strategy.*
