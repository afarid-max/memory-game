# AI Product Management Portfolio Context

## Portfolio purpose

This repository is a small, public-facing AI product management portfolio project built around two familiar browser games: Memory and Snake. It demonstrates product thinking through concise product requirements documents (PRDs), explicit user-facing requirements, acceptance criteria, and working prototypes.

The portfolio is intentionally grounded in artifacts that exist in this repository. It does not claim customer interviews, user research, market sizing, analytics, business results, or professional experience that are not documented here. The games are examples of product definition and prototyping; they are not AI-powered products.

## Intended audience

- Product management and AI product management hiring teams.
- Product, design, and engineering collaborators reviewing how a feature is framed and specified.
- Visitors who want to try the prototypes and compare the requirements with the implemented experience.

## Portfolio projects

### Memory (Concentration)

`memory-game.html` is a standalone pair-matching game with 4x4 and 6x6 boards, a timer, move counter, move-based star rating, completion dialog, local best-score storage, keyboard interaction, and responsive layout.

The two Memory theme documents cover the same light/dark theme initiative from different levels of detail:

- `PRD_new_dark_mode_feature.md` gives an initial feature brief and acceptance criteria.
- `PRD_dark_theme.md` expands the requirements and implementation/validation guidance.

Together, they can be presented as a requirements iteration: define the player problem, account for all themed surfaces and interaction states, keep theme preference separate from score data, and protect existing gameplay.

### Snake

`snake-game.html` is a standalone Snake prototype with a 20x20 canvas board, keyboard and small-screen touch controls, score and best-score persistence, pause/resume, increasing speed, and light/dark themes.

`PRD_snake_game.md` documents the intended audience, scope, gameplay and accessibility requirements, acceptance criteria, and validation approach. The HTML file provides a playable artifact against which those requirements can be reviewed.

## Repository map

- `README.md` — public portfolio landing page, project summaries, and instructions for trying the games.
- `context.md` — this handoff document for future portfolio edits and AI-assisted work.
- `memory-game.html` — Memory game prototype.
- `PRD_new_dark_mode_feature.md` — initial Memory theme requirements.
- `PRD_dark_theme.md` — expanded Memory theme requirements and validation guidance.
- `snake-game.html` — Snake game prototype.
- `PRD_snake_game.md` — Snake product requirements.
- `.gitignore` — ignores common local-only files such as `.DS_Store`, `node_modules`, and log files.

## Product work represented

The artifacts demonstrate:

- Translating a simple player need into a defined feature and scope.
- Writing goals, non-goals, functional requirements, user experience details, and acceptance criteria.
- Considering keyboard access, assistive technology, responsive layouts, persistence, and game-state behavior.
- Connecting a PRD to a working, dependency-free browser prototype.
- Documenting how to validate behavior rather than presenting implementation alone.

The repository does not currently contain discovery notes, personas based on research, experiment results, usage analytics, a roadmap, a business case, or evidence of AI model design/evaluation. Add such portfolio material only when it can be supported by actual work and clearly identify assumptions or illustrative examples.

## Run and review

Open either HTML file directly in a modern browser. No package installation, build step, external service, or network connection is needed. Optionally serve the folder locally:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000/memory-game.html` or `http://localhost:8000/snake-game.html`.

When reviewing a change, compare the prototype behavior with its PRD, try keyboard and touch interactions where applicable, verify light and dark themes, and check a narrow viewport. These are manual prototype checks, not evidence of user validation.

## Guidance for future AI-assisted edits

- Treat the README and PRDs as the source of product intent; flag inconsistencies instead of silently inventing requirements.
- Keep portfolio claims factual, specific, and supported by files or verified work.
- Distinguish observed evidence from assumptions, proposed follow-up work, and illustrative examples.
- Do not add personal contact details, employer/client information, private research, credentials, or other identifying material without explicit review and approval.
- Preserve standalone HTML files and avoid external runtime dependencies unless the project scope changes.
- Keep Memory and Snake behavior independent; their local-storage keys and game state must not collide.
- Update the relevant PRD, README, and this context when scope or behavior changes.
- Validate the exact user-visible requirement in a browser at desktop and mobile sizes before describing it as complete.

## Privacy and publication

Current project content is intended to describe the prototypes without personal contact details. Review new screenshots, examples, and documentation for names, email addresses, employer or client information, private data, and credentials before publishing.

Existing Git history is preserved. Historical commit author metadata is separate from the current project files and was not rewritten as part of this documentation update.
