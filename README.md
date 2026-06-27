# Compound - A Personal Decision Intelligence System

People are consuming more information than ever. Very little of it compounds into better decisions.

Compound transforms everything you read, watch, learn, and decide into a connected intelligence layer that grows more valuable over time. Built on Obsidian and Claude, it automatically links knowledge, mental models, research, and past decisions so the right insights surface when you need them most.

No API keys. No code. No terminal.

---

## In Practice

**A YouTube talk becomes a mental model library.**
You watch a Charlie Munger lecture. You clip it. The system processes it automatically - extracts the key mental models, files them into your vault, and links them to related ideas already there. Next time you're facing a decision, the relevant models surface on their own.

**Scattered research becomes a single living thesis.**
You clip articles, YouTube breakdowns, and podcast snippets on a sector as you find them. The system processes each one - building and sharpening a single page with a current thesis, evidence for, evidence against, and open questions. The eleventh article makes it sharper than the tenth.

**Goals become a working system.**
Set an objective and Claude breaks it into a prioritised task list tracked against a sprint. When you get stuck, relevant mental models and past decisions surface automatically to help you move forward. Every Monday, the system reviews what's complete, flags what's slipping, and tells you what to focus on next.

---

## The Decision System

When you face a decision, tell Claude. It runs a structured framework: classifies the decision type, finds the real underlying problem, forces you to consider a third option, runs a pre-mortem. You set tripwires. You commit with your reasoning written down.

The knowledge and decision layers connect. Mental models you've captured, research theses, and past decisions on similar topics surface automatically as you work through a call. The more you've built in your vault, the richer the context.

Six months later, the system surfaces the note. Was the process sound? What would you do differently? Over time, patterns emerge. You stop making the same category of mistake twice.

---

## Getting Started

**What you need:**
- [Obsidian](https://obsidian.md/download) - a free note-taking app (Mac, Windows, Linux, iOS, Android)
- [Claude Cowork](https://claude.ai/referral/YU4FcS6hQQ) - Claude Pro desktop app

**Setup (15 minutes):**

1. Download the vault: click the green **Code** button on this page, then **Download ZIP**. Unzip to a permanent location on your computer.

2. Open Obsidian, click **Open folder as vault**, and select the unzipped folder.

3. In Obsidian, go to **Settings - Community Plugins** and turn off Restricted Mode. Obsidian will ask you to confirm - accept. The 4 required plugins (Tasks, Dataview, Templater, Homepage) are pre-installed and will enable automatically.

   Also install [Obsidian Web Clipper](https://obsidian.md/clipper) - one-click capture from any webpage or YouTube video.

4. Open the **Claude Cowork desktop app** and create a new project. In Obsidian, open `_system/project-instructions.md`, copy the full contents, and paste into the **Custom Instructions** field in Cowork. Save.

5. Open `FIRST_RUN.md` and follow the steps. Claude interviews you and configures the whole system for your life in one session.

**[Open FIRST_RUN.md to begin →](FIRST_RUN.md)**

**Optional:** [Readwise](https://readwise.io) ($9.99/month) syncs Kindle highlights directly into your vault. Free alternative: export via [Amazon's notebook](https://read.amazon.com/kp/notebook) and paste manually.

---

## How It Works

**Every session picks up where you left off.** Three small files load at the start of every session - who you are, a catalog of your vault, and predefined workflows for common requests. Claude orients in seconds. No re-explaining, no copy-pasting context.

**You control what Claude sees.** Every note has a simple on/off flag. Raw web clippings are invisible to Claude until processed. Your vault can grow to thousands of notes and sessions stay fast.

**Knowledge compounds rather than piles up.** One living page per topic. Every piece of content you process updates it. Ten articles on the same subject become one sharp page. The eleventh makes it sharper.

**Common requests are already wired up:**

| When you say... | Claude does... |
|-----------------|----------------|
| "process this article" | Reads, updates Synthesis, extracts mental models, marks done |
| "prep me for my meeting with [person]" | Loads entity page, surfaces relevant notes, suggests questions |
| "what are we working on this week" | Reads active priorities, gives ranked weekly focus |
| "help me think through [decision]" | Runs structured decision framework, writes note to vault |

**Vault structure:**

```
Second Brain/
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
└── _system/          <- index, log, structure, workflows, task-specs
```

---

## FAQ

**Does this work on mobile?**
Yes. Obsidian has free iOS and Android apps. Your vault syncs via iCloud so notes, tasks, and clippings are on your phone. The Web Clipper works on mobile too. Full automation is desktop only; mobile gives you the thinking layer wherever you are.

**Does this work on Windows?**
Yes. Obsidian runs on Windows, Mac, and Linux. Claude Cowork is available on Mac and Windows. iCloud on Windows can be clunky - OneDrive or Dropbox are smoother alternatives.

**What does it actually cost?**
Obsidian is free. Claude Cowork runs on a Claude Pro subscription. Readwise is optional at $9.99/month. Web Clipper and all Obsidian plugins are free.

**Is my data private?**
Your vault is just files on your computer. Nothing is uploaded unless you choose to sync. Claude processes your notes during sessions but does not retain them between conversations.

**Do I need to know Obsidian?**
No. If you can open a folder and install a browser extension, you're set. [This 15-minute video](https://www.youtube.com/watch?v=z4AbijUCoKU) covers everything you need.

---

## Why I Built This

Every knowledge system I tried was designed for someone else.

The good ones were built for developers - terminal first, config files, command line setup. The no-code ones were rigid templates that worked fine until my goals changed or my information habits didn't fit the structure. None of them adapted to how I actually think, what I'm actually working on, or the specific way I consume information.

I wanted something that started with me - my context, my quirks, my goals - and got smarter the more I used it.

---

*Built by [Sumit Chugh](https://linkedin.com/in/sumitchugh) - founder and independent consultant. I use this system daily to manage research across AI, investing, and venture strategy.*
