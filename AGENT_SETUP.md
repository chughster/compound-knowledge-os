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

Important: the sandbox has no internet access and Terminal blocks typing. Use the following approach instead:

1. Build the install command by substituting `INSTALL_PATH` with the full absolute path I gave in Step 2. If the user confirmed the default, use `$HOME/Documents/Compound Vault` — do not use `~` as it won't expand inside quotes:
```bash
curl -L "https://github.com/chughster/compound-knowledge-os/archive/refs/heads/main.zip" -o /tmp/compound-vault.zip && \
unzip -q /tmp/compound-vault.zip -d /tmp/ && \
mkdir -p "INSTALL_PATH" && \
cp -r /tmp/compound-knowledge-os-main/. "INSTALL_PATH"/ && \
rm -rf /tmp/compound-vault.zip /tmp/compound-knowledge-os-main && \
echo "Done"
```
2. Use the `write_clipboard` computer-use tool to copy the command to my clipboard
3. Ask me to open Terminal and press **Cmd+V** (Mac) or **Ctrl+V** (Windows) to paste and run it
4. Wait for me to confirm Terminal printed `Done`

Then confirm the key files are present: `FIRST_RUN.md`, `_system/project-instructions.md`, `Priorities/priorities.md`.

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
4. The 4 required plugins (Tasks, Dataview, Templater, Homepage) should enable automatically

If any plugin shows an error or fails to enable: click the trash icon next to it to remove it, then click **Browse**, search for the plugin by name, reinstall it, and enable it.

Ask me to confirm all 4 plugins are enabled before continuing.

**Step 5b — Install Web Clipper (manual step)**

Tell me to install [Obsidian Web Clipper](https://obsidian.md/clipper) — a free browser extension for one-click capture from any webpage or YouTube video. It takes under a minute. This is optional but recommended.

**Step 6 — Configure Claude Cowork project**

Tell me to do the following:
1. Open Finder (Mac) or File Explorer (Windows), navigate to the vault install location, and open `_system/project-instructions.md` in any text editor (TextEdit, Notepad, VS Code)
2. Select all and copy the full contents
3. In this Cowork session, look for the **Instructions** field — it appears at the top of the project sidebar or in the project settings panel (not in the chat)
4. Paste the copied text into the **Instructions** field and save

Important: paste into the Instructions field, not into the chat.

Explain that this is the one step that cannot be automated — it wires Claude to the vault.

Ask me to confirm this is done before continuing.

**Step 7 — Run FIRST_RUN**

Once I confirm Step 6 is done, tell me the installation is complete. Then immediately begin the FIRST_RUN setup by reading the prompt in `FIRST_RUN.md` and starting the interview from Area 1.

Do not wait for me to open FIRST_RUN.md manually — just begin.

---

> **End of prompt.**
