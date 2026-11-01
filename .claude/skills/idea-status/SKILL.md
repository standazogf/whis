---
name: idea-status
description: Read-only answers about the Idea Pipeline board - Now/Next/Later, stale and silent cards, ideas without a game plan, progress of one idea, what's open longest. Use for "review my ideas", "how is IDEA-0xx going?", and the ideas block of Whis's briefing.
---

# Idea status (read-only)

Board: https://claude.ai/artifact/EfQsYr61qLFxVMPqqLQK8h, collection `ideas`. This skill never writes.

## Derived fields (compute, don't store)
- **Days open** = today − `firstSeen` (or − `closedAt` if done/parked). Today in America/Guayaquil.
- **Rank / horizon** (captured only): sort by `rank`; 1–5 Now, 6–12 Next, 13+ Later.
- **Stale** = `captured` and open > 21 days. **Silent** = `handed_off` or `in_progress` and `updatedAt` > 14 days ago.
- **No game plan** = `handed_off` or `in_progress` with no steps in `phases`, or no `kpi`.
- **Progress** = steps with `done: true` / all steps; **next step** = first step not done.
- **Overdue step** = not done and `due` < today.
- Research items (`category: "research"`) are reported separately: to research / trying / adopted / skipped.

## Answers
| Ask | Output |
|---|---|
| "review my ideas" | Table sorted by days open: ID, title, status, rank/horizon, days, flag |
| "what's in Now?" | Top 5 with next step each |
| "how is IDEA-###?" | Status, handed to, progress x/y, KPI, next step, overdue steps, last 3 log entries |
| "what's stuck?" | Stale + silent + no game plan + overdue steps |
| "what's open longest?" | Top 5 open by days |
| Briefing block (for Whis) | ≤ 6 lines: moved since yesterday (log dates), overdue steps due tomorrow, silent cards, one nudge |

## Rules
- Cite IDs (IDEA-###). Keep it short; a table only when there are more than 5 rows.
- Don't open diary entries unless Sebastian asks (Whis reads the diary only on request).
- If the database can't be read, say so in one line; never guess.
