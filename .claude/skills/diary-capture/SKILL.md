---
name: diary-capture
description: Save a thought, voice note or typed note as a brain-diary entry (as spoken + English layer + tags), from the diary project or from any chat via the inbox. Use for "anótalo en mi diario", "save this to my diary", or when Whis receives a thought to keep.
---

# Diary capture

Turns a raw dump into an entry in Sebastian's brain diary (Claude project "Ideas & Thoughts Repository (My brain diary)"). Rules live in that project's `claude/00-how-this-diary-works.md`; if they differ from this skill, the manual wins.

## Where to write
- **Session attached to the brain diary project** → write the entry straight into `claude/entries/YYYY-MM.md` (Projects tool).
- **Any other chat (e.g. Whis)** → write it to the inbox: Idea Pipeline board https://claude.ai/artifact/EfQsYr61qLFxVMPqqLQK8h, collection `diary_inbox`, one document per dump (`doc_id` = `IN-YYYYMMDD-HHMM`), fields `{text, receivedAt, source, language}`. The diary project files it on its next session (step 0 below). Never drop a thought because the project isn't attached.

## Steps
0. **(Diary project only) Empty the inbox first:** list `diary_inbox`; file each item as an entry with steps 1–6, then delete it from the inbox (pinned delete).
1. **Capture as spoken.** Keep the original language (ES/EN). Fix dictation errors lightly; don't rewrite his voice. If one dump covers several topics, split into several entries with the same timestamp. Long reflections stay one entry with a 2–3 bullet summary.
2. **ID and date.** `E-YYYYMMDD-NN` (next free NN for that day; read the month file). Time in America/Guayaquil.
3. **English layer:** type (idea · reflection · fear · goal · decision · lesson · observation · question · gratitude), area (work · growth · life · idea), tags, people, one-line summary, related entries and `thread:<slug>`.
4. **Context (optional):** if it follows a meeting, add `**Meeting:** <title, date>` from Granola; calendar from Outlook. Never paste transcript text. If a connector fails, skip it.
5. **Append** to `claude/entries/YYYY-MM.md`, newest on top (read the file, add, write the full file back). Format:
   ```
   ### E-YYYYMMDD-NN · <short title>
   - **Date:** YYYY-MM-DD HH:MM (America/Guayaquil)
   - **Type:** … | **Area:** … | **Tags:** #… #…
   - **People:** …
   - **Summary (EN):** …
   - **Meeting / Calendar:** (optional)
   - **Idea:** IDEA-### | —
   - **Related:** E-…, thread:<slug>

   > Original text, as spoken

   **Trigger:** (optional pasted snippet)
   **Notes:** thinking-partner contribution
   ```
6. **Follow-ons:** update `claude/03-index.md` if the entry opens, advances or closes a thread, goal, fear or decision; if it's an idea, call `idea-register`.
7. **Reply:** one thinking-partner line (a sharp question, a link to an earlier entry, a tension, or a reframe with his DNA; skip for gratitude and logistics), then confirm in one line: "Saved as E-… (type, tags)."

## Rules
- Store everything, including confidential deal details and health; no code names.
- Pasted snippet with no comment → ask one question: "What's the thought?"
- Personal, family, health and thoughts about colleagues never leave the diary.
- From the inbox path, reply only "Saved to your diary inbox; it'll be filed next time you open the diary."
