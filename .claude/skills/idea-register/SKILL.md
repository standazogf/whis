---
name: idea-register
description: Register an idea on the Idea Pipeline board with the next IDEA/RES ID, or attach it to an existing card if it matches. Use when a diary entry is an idea, or for "add this idea", "registra esta idea", "is this already on my board?".
---

# Idea register

Board: https://claude.ai/artifact/EfQsYr61qLFxVMPqqLQK8h, collection `ideas` (ArtifactData). Rules: brain diary `claude/00-how-this-diary-works.md` (manual wins if they differ).

## Steps
1. **Read the whole collection** (`list`, limit 200). Note each card's `version`.
2. **Match check.** Compare the new idea with every open and closed card (title, summary, log). Same goal or same tool = match, even with different words.
   - **Match** → don't create. Update that card (pinned): add the diary entry ID to `sources`, add a log entry `{date, text: "New mention (E-…): <one line>"}`. Say: "Matches IDEA-###, added to it."
   - **Partial overlap** → ask once: "New card, or part of IDEA-###?"
   - **No match** → create.
3. **Kind.** Something to build → `IDEA-###`. A tool or topic to look into → `RES-###` with `category: "research"`. Next free number = max existing + 1.
4. **Create** (no `if_version` on create):
   ```json
   {"ideaId":"IDEA-###","title":"","summary":"why it matters, 1–3 sentences",
    "category":"ai|process|team|culture|other|research",
    "theme":"IAtízate DE|Agents for the team|My own agents|Finance|DE operations|Holding|Other",
    "priority":"H|M|L","status":"captured","rank":<last open rank + 1>,"horizon":"later",
    "firstSeen":"YYYY-MM-DD","sources":["E-…"],"dependsOn":[],
    "handedTo":"","handedAt":"","handoffDoc":"","closedAt":"","owner":"Sebastian",
    "kpi":"","targetDate":"","phases":[],
    "log":[{"date":"YYYY-MM-DD","text":"Captured from E-…."}],
    "createdAt":"ISO -05:00","updatedAt":"ISO -05:00"}
   ```
   New ideas enter at the bottom of the ranking unless Sebastian says where (then shift ranks and recompute horizon: 1–5 now, 6–12 next, 13+ later, in one batch).
5. **Link back:** put the ID in the entry's `**Idea:**` line and add the row to the idea table in `claude/03-index.md` (diary project only).
6. **Confirm in one line:** "IDEA-### captured (theme, priority, rank N)."

## Rules
- Never write a game plan here; the build chat writes it at hand-off.
- Card text stays free of private reflections about people.
- Merging two cards: park the younger one with log "merged into IDEA-…", move its sources to the survivor.
- Pin every write to an existing card with `if_version`; on a version clash, re-read and redo.
