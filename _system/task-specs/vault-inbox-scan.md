---
type: note
date: YYYY-MM-DD
status: processed
llm_context: true
tags: [system, scheduled-task, inbox-scan]
---

# Task Spec: Vault Inbox Scan

*Full instructions for the vault-inbox-scan scheduled task. Edit this file to change task behaviour.*

Read `_system/vault-structure.md` to get the current folder map and exclusion rules. Read `Priorities/priorities.md` to know the active sprint goal.

---

## Step 1 — Inbox items

Find all .md files (respecting vault-structure.md exclusions) where status is inbox — match both `status: inbox` and `status: "inbox"` (Obsidian Web Clipper quotes values). List by folder, filename only.

## Step 2 — Missing llm_context

Find any .md files outside excluded folders with no `llm_context` field. These notes are invisible to sessions until fixed. List them; suggest the correct value based on folder and content type.

## Step 3 — Index coverage

Compare wiki notes on disk (Syntheses/, Mental Models/, Investment Ideas/, Books/, Learnings/, Decisions/) against `_system/index.md`. Fix both directly: add missing lines, remove dead lines pointing at files that no longer exist. Report what was fixed.

## Step 4 — Quick wins

From the inbox items in Step 1, flag any file under 2KB that is clearly categorisable. Suggest destination folder based on vault-structure.md (no invented folders).

## Step 5 — Discard cleanup

Scan all files in `Mental Models/` for notes where `curation: "Discard"`. Permanently delete each one and remove their lines from `_system/index.md`. Report how many were deleted and list their names.

---

After the scan, append one entry to `_system/log.md`: `## [YYYY-MM-DD] lint | inbox scan` with a 1-line result.

If Steps 1–5 all return nothing to act on, output: "Vault clean. Nothing to action." and stop.

Keep the full report under 250 words. End with: "Say 'process inbox' to work through unprocessed items."

Do not make any changes to files other than: deleting Discard mental models, index.md coverage fixes, and the log.md entry.
