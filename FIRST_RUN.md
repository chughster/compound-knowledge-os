# First Run Setup

You've installed Obsidian, opened the vault template, and configured your Claude project with the system prompt. Now you need to configure the system for your life.

Paste the prompt below into your Claude project. Claude will interview you and generate all your config files in one session.

---

## Before You Start — Which Claude Are You Using?

**Claude Cowork (desktop app) — recommended**
Claude has direct file access to your vault. It will write your config files automatically during setup. Nothing to copy or paste manually.

**Claude.ai Projects (web)**
Claude can generate your config files but cannot write them to disk. At the end of setup, Claude will show you each file's content. Copy each one into Obsidian manually — create the file at the path shown, paste the content, save.

Either way works. Cowork is faster.

---

## Step 1 — Configure Your Claude Project

1. Go to [claude.ai](https://claude.ai) → **Projects** → **New Project**
2. Open `_system/project-instructions.md` from this repo
3. Copy the full contents and paste into the project's **Custom Instructions** field
4. Save

---

## Step 2 — Run Setup

> Copy everything below this line and paste it into your Claude project.

---

I've just set up the Knowledge OS vault template from GitHub and I'm ready to configure it for my life. You're going to guide me through the full setup.

Here's what I need you to do:

**Step 1 — Ask me questions.** You'll interview me across four areas. Ask them one area at a time, not all at once. Wait for my answers before moving to the next area.

**Step 2 — Generate my config files.** Once you have everything you need, generate and write the following files directly to the vault:
- `Context/CONTEXT.md` — my identity, priorities, working style
- `_system/fast-paths.md` — workflows tailored to my domains
- `_system/index.md` — a skeleton catalog with my initial note structure
- `Priorities/priorities.md` — my top priorities as tasks with tags and due dates

**Step 3 — Create my folder structure.** Based on what I tell you, suggest which optional folders to activate and which to skip. Then create a brief `_system/log.md` entry marking the setup as complete.

---

**Start with Area 1: Who You Are**

Ask me:
- My name and where I'm based
- What I do for work — my role, what I run, who I work with
- Whether I'm employed, freelancing, running a business, or some combination
- What I'm trying to accomplish in the next 3–6 months — the strategic picture, broad goals and outcomes

After I answer, move to Area 2.

---

**Area 2: What's Active Right Now**

Ask me:
- What's the single most pressing thing in my life right now — the thing that keeps me up at night or should be getting the most of my attention
- What projects or initiatives am I actively working on
- Are there any hard deadlines coming up in the next 60 days
- What would "a great month" look like for me

After I answer, move to Area 3.

---

**Area 3: What I Track and Learn**

Ask me:
- What topics do I read about, watch, or follow regularly (give examples: AI, finance, health, cooking, history, etc.)
- Do I track investments or a portfolio — if so, what kind (stocks, crypto, real estate, etc.)
- Are there specific people, companies, or domains I want to keep a running file on
- Do I take meeting notes — if so, what kind of meetings (client, team, personal)
- Are there any recurring decisions I make that I'd like a system for (e.g. buying decisions, hiring, project prioritisation)

After I answer, move to Area 4.

---

**Area 4: How I Work**

Ask me:
- How do I prefer AI to communicate with me — detailed and thorough, or short and direct
- Am I comfortable editing markdown files directly in Obsidian, or do I prefer to do everything through chat
- Do I want weekly automated check-ins (priorities review + learning recap), or would I rather trigger these manually
- Is there anything I definitely don't want the AI to do, surface, or store

---

**After all four areas, do the following:**

1. Summarise what you've learned about me in 5–7 bullet points. Ask me to confirm or correct anything before writing files.

2. Once confirmed, generate and write all four config files to the vault. Show me each file as you write it.

3. Suggest 3–5 fast-path workflows that match my specific domains and situation. Explain what each one does and ask which ones I want to activate.

4. Tell me what to do next — the first three things I should put into the vault to get value out of it immediately.

Ready when you are. Start with Area 1.

---

## What Gets Created

By the end of this session, you'll have:

| File | What it contains |
|------|-----------------|
| `Context/CONTEXT.md` | Your identity, ventures, priorities, working style — the file Claude reads first in every session |
| `_system/fast-paths.md` | Domain-specific workflows tailored to your life |
| `_system/index.md` | A catalog skeleton Claude updates as your vault grows |
| `Priorities/priorities.md` | Your top priorities as tasks, tagged and dated |
| `_system/log.md` | Setup log entry marking day zero |

Setup takes 10–15 minutes. After that, your vault is live.
