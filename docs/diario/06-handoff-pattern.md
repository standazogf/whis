> Copy of the brain diary doc `claude/06-handoff-pattern.md`, 01-nov-2026. The original wins. Differs from the original in one line (Diana Correa owner rule: private planning guidance removed).

# Handoff Pattern — spec for the context agent

_What Sebastian's project handoff documents have in common, derived from three examples dated 2026-10-31 (in `claude/context/`), plus the planning method merged in from the retired "Ideas Organizer" (game plan) project on 2026-10-31. The context agent (diary E-20261031-03) and the future `idea-handoff` skill use this to interview Sebastian and write a tailor-made handoff for each new project. Last updated: 2026-10-31._

## What a good handoff does
A single Markdown file that lets a new Claude project (or agent) start working without asking basic questions. It is a **snapshot with a date**, it **names its sources**, and it says **which source wins** if they disagree. It ends by asking the receiving chat for a **game plan first** and telling it to **report back** on the Idea Pipeline card.

## Sections the three examples share (+ two required ones)
| # | Section | What goes in it | Seen in |
|---|---|---|---|
| 0 | Title + date + source line | "Handoff — <project> (al DD-mmm-YYYY)"; built from N docs; live docs win | all 3 |
| 1 | What this is | Purpose, parent program, vision/motto, duration, phase (e.g. ADKAR stage), how this project fits | all 3 |
| 2 | People | Table: name, title, role in the project; who is guest, support, sponsor; email list if the project sends emails | all 3 |
| 3 | Timeline / calendar | Past milestones and upcoming dates with status | all 3 |
| 4 | What happened so far | Session-by-session or phase-by-phase outcomes, decisions, numbers | Desayuno, DE AI LABS |
| 5 | Live documents & assets | Links to artifacts and files, which one is the official base | all 3 |
| 6 | Shared definitions / frameworks | Vocabulary the team uses (agent = 6 pieces, DRAG, PRIME…) | all 3 |
| 7 | How Claude works here (rules) | Plan before build; emails as drafts in his voice; language; design system to use; what never to publish | all 3 |
| 8 | Confidentiality | What must never appear in team-facing material | all 3 |
| 9 | Voice / tone | Greetings, closings, phrasing, typos not to copy | Desayuno, DE AI LABS |
| 10 | Technical lessons | Tools, folders, scripts, known failure modes | Desayuno |
| 11 | Open items / pending decisions | What's pending, by whom, by when | all 3 |
| 12 | **First deliverable: game plan** (required) | The block below, copied in | new 2026-10-31 |
| 13 | **Report back** (required) | Card ID, board link, what to write when | new 2026-10-31 |

## Interview the context agent should run (one round)
1. **Name and purpose:** what is the project, and what does "done" look like?
2. **Parent and siblings:** which existing program or projects does it belong to or depend on?
3. **People:** who is involved, in what role, and who must never see what?
4. **Dates:** what's the deadline and the next milestone?
5. **Sources:** which folders, artifacts, projects, meetings or emails hold the context? Are those folders connected? (Check before writing; diary E-20261031-09.)
6. **Outputs:** what will Claude produce here (decks, emails, sites, analyses), and in which design system / format?
7. **Rules and voice:** language, tone, approval rules, confidentiality limits.
8. **Open questions:** what's undecided right now?

Then: pull everything relevant from the projects wiki, keep only what this project needs, write the handoff in the language of the deliverables (Spanish for GF projects unless told otherwise), list sources and date, and end with open items, the game-plan block and the report-back block.

## Game plan — the required first deliverable of every build chat
_Merged from the Ideas Organizer project (its "lean roadmap"). This project does not write the plan; the chat that builds the idea does, as its first output, before building anything. The board's **Hand off** message carries the short version of this block; full handoff files carry it whole._

**Trigger:** every hand-off (quick or full). An idea that reaches the Now cut line without a hand-off gets no plan here; the plan is written where the work happens.

**Steps in the receiving chat**
1. **Understand.** One round of questions (purpose and the one result that proves it worked, people, dates, sources, outputs, rules). Ask only what can't be assumed; otherwise assume and state the assumptions.
2. **Fit test.** It serves the DE Purpose, strengthens at least one pillar, reflects the principles and DNA (`02-work-context.md`).
3. **Classify.** Category (ai / process / team / culture / other), theme, pillar(s), priority H/M/L, depends on.
4. **Draft the lean game plan (about one screen):**
   - exactly **one success KPI** (measurable, target, date);
   - **3–5 phases**, starting with a quick, imperfect pilot Sebastian can self-approve (no approval phase for experiments);
   - every step has **one owner and a due date**;
   - for tech ideas: **learning-by-building** (build together, pairing, demos, rotating presenter), **guardrails** (human review, validation, a how-it-works doc) and **IT as a partner**, not a gate;
   - a consensus moment with the team ("consenso prima") for team ideas;
   - **ends in something real** (a working tool) **plus a person who can build or maintain it** — never a report;
   - Claude only, no-code/low-code first, build rather than buy; keep bold ideas bold in the simplest version that works ("simplificamos").
5. **Approve, then write to the card** (ArtifactData, `ideas/IDEA-###`, read first, pin `if_version`): `kpi`, `owner`, `targetDate`, `phases: [{name, steps: [{id, text, owner, due, done:false}]}]`, `status: "in_progress"`, log "Game plan approved". The card's detail panel shows the plan with tickable steps.
6. **Track.** Tick steps (`done: true`) and log each milestone; if the plan changes, update `phases` and log why.

**Chat layout (lean)**
```markdown
## IDEA-### — <title>
**Category · Theme · Pillar(s):** … · **Priority:** H/M/L · **Owner:** … · **Target:** YYYY-MM-DD
**Success KPI (one):** <result + target + date>
**Assumptions:** … · **Depends on:** IDEA-… or —

### Phase 1 — Pilot (<weeks>)
| # | Step | Owner | Due | Done |
|---|---|---|---|---|
| 1.1 | … | … | YYYY-MM-DD | ☐ |
### Phase 2 — Build / learn-by-building
### Phase 3 — Guardrails (review, validation, how-it-works doc)
### Phase 4 — Roll out: consensus + show-and-tell (optional)
### Phase 5 — Hand over / maintain (optional)

**Ends in:** <the real thing> + <who maintains it>
```

**Owner rules**
- Only DE team members own steps: Sebastian Tandazo, Diana Narvaez, Diana Correa, Beliza Coro, Jorge Romero, Paola Lara, Diego Hidalgo. Never anyone outside DE (whether Ignacio Paz, Abigail Mena, Pablo Yepez or Ignacio Ballesteros may own steps is open).
- **Personal tools** (theme "My own agents"): Sebastian owns every step.
- **Team ideas:** spread ownership; don't default to Sebastian. Diana Narvaez co-owns the biggest initiatives; Beliza Coro is the natural owner for DEI and culture; Jorge Romero brings energy/project-finance; Paola Lara is the pilot user for analyst and AI workflows; Diego Hidalgo owns PMO, tracking and cadence steps.
- **Diana Correa:** sponsorship and visibility roles, not execution-heavy steps.
- Everyone is beginner–intermediate: design no-code first and rotate who demos and teaches.

**Definition of done:** a working result exists, someone on the team can maintain it, and the log links to it (status `done`, `closedAt`). Whether the KPI must be hit before `done` is still open.

## Report back (copy into every handoff)
> This chat develops **IDEA-###** on Sebastian's Idea Pipeline board: https://claude.ai/artifact/EfQsYr61qLFxVMPqqLQK8h (collection `ideas`, document `IDEA-###`). Use the ArtifactData tool (read first, pin `if_version`):
> - first deliverable: the game plan above; when Sebastian approves it, write `kpi`, `owner`, `targetDate`, `phases`, `status: "in_progress"` and a log entry;
> - after each milestone: tick the steps done and add a log entry `{date, text}`;
> - when delivered: `status: "done"`, `closedAt` (YYYY-MM-DD) and a log entry with the link to the result and who maintains it.

## Rules
- Tailor, don't dump: include only the parts of the wiki the new project needs.
- Never copy diary content (personal reflections, thoughts about colleagues) into a handoff unless Sebastian asks.
- Keep one consistent name per agent or person; flag inconsistencies between sources instead of picking silently (e.g. "Louis Litt" vs "Suits", "Mary Poppings" vs "Mary Poppins").
