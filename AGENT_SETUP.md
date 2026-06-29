# Agent-Assisted Setup

If you have Claude Cowork installed, paste the prompt below into the chat of your new Cowork project. Claude will handle the download, installation, and vault configuration automatically.

> **📋 Copy everything between the lines below and paste it into a new Claude Cowork session.**

---

I want to install the Compound Vault — an open-source Personal Knowledge OS built on Obsidian and Claude. Please handle the installation for me.

Here is what I need you to do, step by step:

**Step 1 — Check prerequisites**

Check whether Obsidian is installed on my computer by looking for it in `/Applications/Obsidian.app` (Mac) or `C:\Users\<name>\AppData\Local\Obsidian` (Windows). If it is not installed, stop and tell me to install it from https://obsidian.md/download before continuing.

**Step 2 — Choose install location**

Ask me where I want to put the vault. Default suggestion: `~/Documents/Compound Vault`. Wait for my answer before proceeding.

**Step 3 — Download and install**

Using bash:
1. Download the ZIP from `https://github.com/chughster/compound-knowledge-os/archive/refs/heads/main.zip` and save it to a temporary location
2. Unzip it — this will create a subfolder named `compound-knowledge-os-main/` containing the vault contents
3. Move the **contents** of `compound-knowledge-os-main/` (not the wrapper folder itself) to the install location I specified in Step 2
4. Confirm the folder exists and the key files are present (`FIRST_RUN.md`, `_system/project-instructions.md`, `Priorities/priorities.md`)

**Step 4 — Open in Obsidian (manual step)**

Tell me to do the following:
1. Open Obsidian
2. Click **Open folder as vault** on the welcome screen (or go to **Settings - Change vault** if Obsidian is already open)
3. Navigate to and select the folder I chose in Step 2

Obsidian cannot register a new vault automatically — this one click is unavoidable.

Ask me to confirm the vault is open in Obsidian before continuing.

**Step 5 — Enable plugins (manual step)**

Tell me to do the following in Obsidian:
1. Go to **Settings** (gear icon, bottom left)
2. Click **Community Plugins**
3. Click **Turn off Restricted Mode** and confirm
4. The 4 required plugins (Tasks, Dataview, Templater, Homepage) will enable automatically

Ask me to confirm this is done before continuing.

**Step 5b — Install Web Clipper (manual step)**

Tell me to install [Obsidian Web Clipper](https://obsidian.md/clipper) — a free browser extension for one-click capture from any webpage or YouTube video. It takes under a minute. This is optional but recommended.

**Step 6 — Configure Claude Cowork project**

Tell me to do the following:
1. In this Cowork session, go to **Project Settings**
2. Open the file `_system/project-instructions.md` from my vault
3. Copy the full contents and paste them into the **Custom Instructions** field
4. Save

Explain that this is the one step that cannot be automated — it wires Claude to the vault.

Ask me to confirm this is done before continuing.

**Step 7 — Run FIRST_RUN**

Once I confirm Step 6 is done, tell me the installation is complete. Then immediately begin the FIRST_RUN setup by reading the prompt in `FIRST_RUN.md` and starting the interview from Area 1.

Do not wait for me to open FIRST_RUN.md manually — just begin.

---

> **End of prompt.**
