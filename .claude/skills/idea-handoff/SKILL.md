---
name: idea-handoff
description: Hand an Idea Pipeline idea (IDEA-###) to another chat or project - quick kickoff message or full handoff file, with a game plan as the build chat's first deliverable.
---

# Idea hand-off

Use when Sebastian says "handoff IDEA-### to <project/chat>", "IDEA-### → <project>", "full handoff IDEA-###", or when Whis routes an idea to be built.

The brain diary project is the repository, not the workshop. This skill never builds the idea and never writes its game plan. It packages the idea so the receiving chat writes the game plan first and reports back on the board.

## Sources
- Board: https://claude.ai/artifact/EfQsYr61qLFxVMPqqLQK8h, collection `ideas`, doc `IDEA-###` (ArtifactData).
- Brain diary docs: `claude/06-handoff-pattern.md` (sections, interview, game-plan block, owner rules, report-back block — source of truth; it wins over this skill), `claude/03-index.md`, `claude/05-ai-program-context.md`, the entries in the card's `sources`.

## Steps
1. **Read the card** (note `version`). If `done` or `parked`, stop and say so. If it already has `handedTo`, ask whether to re-hand it.
2. **Mode.** Quick (default; existing projects that know the context): no file. Full (new project, lots of context, or "full"): a handoff file.
3. **Full mode only:**
   - One-round interview from `06-handoff-pattern.md` (skip what the diary answers; state assumptions).
   - Write `claude/handoffs/IDEA-###-<slug>.md` with the shared sections, tailored, in the language of the deliverables (Spanish for GF projects).
   - Copy in the **First deliverable: game plan** and **Report back** blocks, filled with the card ID. Personal tools (theme "My own agents"): Sebastian owns every step; team ideas: include the owner rules.
   - Never include diary-private content unless Sebastian asks.
   - Save with `project_write`; give Sebastian the file to upload in the receiving chat.
4. **Update the card** (one pinned write): `status: "handed_off"`, `handedTo`, `handedAt` (today, America/Guayaquil), `handoffDoc` (full mode), log "Handed off to <dest> (quick|full)."
5. **Kickoff message** to paste as the first message there — same text as the board's Hand off button: ID, title, summary, depends on, diary sources, handoff file (if any), the FIRST DELIVERABLE — game plan block (one-round interview; one KPI; 3–5 phases, pilot first; one owner + due date per step, DE team only; learning-by-building, guardrails, IT as partner for tech ideas; ends in something real + maintainer; Claude only, no-code first) and the report-back block (write the approved plan to the card, tick steps + log per milestone, `done` + `closedAt` + link + maintainer).
6. **Confirm in one line:** "IDEA-### → <dest>. Paste the message there (and upload the file)."

## Rules
- Read before every write; pin `if_version`; on a clash re-read and redo.
- One hand-off per call. Don't change rank, priority or theme.
- If called by Whis or another orchestrator: return the kickoff message and file path, skip the interview, and list the open questions for Sebastian.
