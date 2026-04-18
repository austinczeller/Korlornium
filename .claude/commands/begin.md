# /begin — Vault Startup Routine

You are starting a work session in the Korlornium Obsidian vault. Follow these steps in order.

## Step 1: Load context

Read these two files:
- `z_Assests/CLAUDE.md`
- `z_Assests/To Do.md`

## Step 2: Check for completed sessions

Read the memory file at `C:\Users\austi\.claude\projects\C--Users-austi-Documents-Korlornium\memory\last_session.md` (it may not exist yet — that is fine, treat it as if last seen session was 0).

Then list all files in the `Sessions/` folder. Find the highest-numbered session (e.g. "Session 20- At Sea.md" → 20). Compare it to the last seen session number in memory.

If the most recent session number is **greater** than the stored value:
- Read the new session file(s)
- Check whether the `# Recap` section has content (more than a placeholder line). If the Recap is filled in, the session has been played.
- If played: announce which session(s) appear to have been completed and ask the user if they would like to generate a session recap now. Wait for their answer before proceeding.
- Then update the memory file `last_session.md` with the current highest session number (create it if needed, using the frontmatter format with type: project).

If no new sessions: note that there are no new sessions since last time.

## Step 3: To Do review

Scan `z_Assests/To Do.md`. Call out any tasks that look like they may have been completed based on what you can observe in the vault (e.g., a template that now exists, a note that has been written). List them and ask if the user wants to mark them done. Do NOT modify the file without confirmation.

## Step 4: Summary

Give a brief (3–5 line) status summary:
- Current session number
- Any open tasks that seem most actionable today
- Whether a recap is pending

Then wait for the user's direction.

---

## Session Recap Format (use this if the user confirms a recap)

When writing a session recap, read the completed session note fully. Then write:

**Session [N] Recap — [Session Title]**

1. **What happened** — 3–5 sentence narrative summary of the session events, written in past tense, as if for a campaign log.
2. **Key decisions & consequences** — Bullet list of meaningful choices the party made and their outcomes or pending consequences.
3. **NPCs introduced or changed** — Any NPC whose status, attitude, or knowledge changed this session.
4. **Loose threads** — Plot hooks, unanswered questions, or things the world should react to.
5. **Notes for the vault** — Specific things that should be added or updated in the database (NPCs, locations, items, plot lines). Do not make these changes — just list them for the user to approve.
