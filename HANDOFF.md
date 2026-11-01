# Whis – Handoff from the claude.ai build chat (01-nov-2026)

Cleaned on purpose: no budgets, deal details, board figures, family-office data or diary content. Those stay in Sebastian's Claude projects; Whis reads live data through his connectors.

## 1. What Whis is
Sebastian's chief of staff and top orchestrator. He does not track pending items (Pendientes GF ST does that); he makes them happen: nightly briefing, decisions, scheduling, meeting prep and routing to the right agent. See `docs/01_mapa.md`.

## 2. Decisions so far
| Date | Decision |
|---|---|
| 31-oct | Name: Whis (chosen over Oracle, Shion and others). |
| 31-oct | Merges the 9-oct idea: evening "how my day looks + decisions" brief and a scheduling skill (proposes slots, drafts invites, never sends). |
| 01-nov | Split: Pendientes GF ST keeps track of what is open (may become its own agent); Whis reads it and makes it happen. |
| 01-nov | Briefing at 8 pm the night before, Sun–Thu; Sunday adds the week ahead. Runs in the cloud with the computer off. |
| 01-nov | Retire the morning brief skill after Whis passes testing. |
| 01-nov | Whis sits above everyone. Today he routes straight to current agents and skills; rows switch to Perry White and the IAtízate DE coordinator when they exist. |
| 01-nov | Build in Claude Code as a cloud scheduled task, in this private repo. Cloud environment "WHIS" already created (limited network, no setup script, no variables). |
| 01-nov | Build method: the GF agent blueprint (map → design with Q-questions → OK → build v0.1.0 → trap tests + real nights → v0.2.0 → release). |
| 01-nov | Cloud adaptations: no questions at 8 pm (they go into the briefing); written standing sources; briefings never in Git; nothing needed at 8 pm lives on the PC. |
| 01-nov | Four diary skills added (diary-capture, idea-register, idea-status, idea-handoff). Whis writes to the Idea Pipeline only through them, only in live sessions. `idea-status` feeds the briefing's ideas block. |
| 01-nov | Copy the diary docs `00-how-this-diary-works.md` and `06-handoff-pattern.md` into `docs/diario/` (originals win). |
| 01-nov | `idea-handoff` full mode allowed: the handoff file is published as a private artifact and linked in the card's `handoffDoc`. |
| 01-nov | Idea Pipeline board is private and must stay so while `diary_inbox` lives there. |

## 3. Roadmap (IDEA-028)
| Step | Status |
|---|---|
| w1 Private repo `whis` + GitHub access for cloud sessions + CLAUDE.md | In progress (this package) |
| w2 Map `docs/01_mapa.md` | Drafted v0.1, waiting for Sebastian's OK |
| w3 Design `docs/02_diseno.md` with Q-questions → OK | Next |
| w4 Build v0.1.0 | – |
| w5 Trap tests, then 3–5 real nights | – |
| w6 Feedback → v0.2.0 | – |
| w7 Release, schedule Sun–Thu 8 pm, retire morning brief | – |

## 4. Open questions for the design
1. Where the briefing is delivered (email to himself, Teams message, push + page).
2. Briefing language (English or Spanish).
3. Can a cloud run read/write the artifact databases (Pendientes, Idea Pipeline) and SharePoint? Test in the first dry run.
4. Commitments Whis tracks: only what the sources show, or also a hand-kept list.
5. Agent names differ between handoffs: Louis Litt / Suits, Pacari Radar DEI / Radar, Mary Poppings / Mary Poppins, Vision (WACC) / Visión (~90 companies). Which is current?
6. Nicolás Mora (GF Studio): role, and does Whis route to him?
7. Exact Claude Code tool names for Outlook send/forward/accept, to block them in `.claude/settings.json`.
8. Local folder for tests and releases.

## 5. Ecosystem Whis routes to
- **GF Studio:** Mu (valuations, GF decks), Kiki (modern GF design), Lois Lane (storyline), John Stewart (free creative), Amazo (style library), Nicolás Mora (to confirm), Perry White (planned orchestrator).
- **Lucius Fox:** Equisuiza board (Wednesday check).
- **Dobby:** Desayunos con Skills DE (plugin `dobby-desayunos`, on demand, no scheduled tasks).
- **Skills:** `reply-in-my-voice`, `actualizar-pendientes`, `de-ai-labs-video-post`, `de-ai-labs-website`, `youtube-video-to-pptx-summary`, `project-context-sync`, the four diary skills.
- **No agent yet:** IAtízate (holding program) – lives in the Claude project "GF IA Cultural Transformation".
- Other agents are Cowork plugins: at 8 pm Whis only names the route; the hand-off happens in a live session.

## 6. Scheduled tasks already running
| Task | When | With Whis |
|---|---|---|
| Actualizar Pendientes GF ST | Weekdays 7:20 am, cloud | Keep; Whis reads its result |
| Actualizar DE AI LABS Tracker | Weekdays 7:45 am | Keep |
| Morning brief skill | Mornings | Retire after testing |
| Equisuiza check (Lucius) | Wednesdays | Keep; Whis reports it |
| Weekly Brain Diary Recap | Sundays 5:50 pm | Keep separate (private) |

## 7. Known dates (verify against Outlook – sources win)
| Date | Item |
|---|---|
| ~3-nov | IAtízate email to Juan Carlos Berru (draft in Outlook; Sebastian attaches 3 files and sends) |
| Thu 5-nov 16:00 | IE masterclass registration deadline |
| Tue 10-nov 15:00–16:30 | IE masterclass, Edificio Equisuiza |
| Wed 11-nov 9:00–11:00 | Desayuno 3 "Tu agente crece" (place to confirm) |
| 15-nov | Sebastian starts coaching each hackathon participant |
| 31-dic | End of Sprint 1 |
| ~15-ene-2027 | Hackathon DE AI LABS (date to confirm) |

## 8. People (for routing and drafts)
Juan Carlos Berru (CEO, Sebastian's boss) · DE team: Diana Correa, Diana Narváez, Beliza Coro, Jorge Romero, Paola Lara, Diego Hidalgo (external PM) · Guests: Ignacio Paz, Abigail Mena, Mauricio Ruiz · Tech: Pablo Yepez, Ignacio Ballesteros.

## 9. Email voice (short)
Spanish; "tú" with individuals, "ustedes" to the team. Greetings "Estimado X," / "Querido Equipo,"; closes "Saludos," or "Saludos Cordiales,". Drafts end at the sign-off with an empty line (Sebastian adds his Outlook signature). No emojis in the body. English only if the incoming email is in English. Full guide: `reply-in-my-voice` skill.

## 10. Next steps in Claude Code
1. Create the private GitHub repo `whis` and push this folder (Claude Code does the Git work).
2. Make sure cloud sessions have GitHub access (Claude GitHub App or `/web-setup`).
3. Add the two diary docs to `docs/diario/` (check they hold rules only, no entries).
4. Sebastian reviews and OKs `docs/01_mapa.md` → tick w2 on IDEA-028.
5. Write `docs/02_diseno.md` with Q-questions (section 4 + blueprint questions) → Sebastian's OK → tick w3.
6. Copy the reusable GF skills (`gf-acceso`, `gf-redaccion`, `gf-actualizaciones`) from the `gf-studio` repo at a tagged version during the build.
