# AI Product Management Portfolio

A compact portfolio project demonstrating product requirements, feature definition, accessibility considerations, and working browser prototypes through two familiar games: Memory and Snake.

The work in this repository is limited to the artifacts listed below. It does not claim user research, market validation, business outcomes, or AI-powered gameplay.

## Featured projects

### Memory: Concentration

A responsive pair-matching game with 4x4 and 6x6 boards, timer, move count, star rating, keyboard interaction, local best scores, and a light/dark theme.

- **Try it:** [memory-game.html](memory-game.html)
- **Initial theme brief:** [PRD_new_dark_mode_feature.md](PRD_new_dark_mode_feature.md)
- **Expanded theme requirements:** [PRD_dark_theme.md](PRD_dark_theme.md)

The theme documents show how a visual feature can be scoped around consistent surfaces, accessible interaction, persistence, and preservation of existing game state.

### Snake

A responsive, standalone Snake game with keyboard and touch controls, score and best-score persistence, pause/resume, increasing speed, and light/dark themes.

- **Try it:** [snake-game.html](snake-game.html)
- **Product requirements:** [PRD_snake_game.md](PRD_snake_game.md)

The PRD defines the intended game behavior and acceptance criteria; the HTML prototype makes the experience directly playable.

## Product work demonstrated

- Goals, non-goals, user experience, functional requirements, and acceptance criteria.
- Translating feature intent into a working prototype.
- Accessibility and responsive interaction considerations.
- Local persistence and preservation of existing behavior.
- Validation guidance tied to observable product behavior.

For project boundaries, file inventory, and guidance for future AI-assisted updates, see [context.md](context.md).

## Play the prototypes

Open either HTML file in a modern browser. Both games are self-contained and require no installation or network access.

Alternatively, run a local server from the project folder:

```bash
python3 -m http.server 8000
```

Then visit:

- Memory: <http://localhost:8000/memory-game.html>
- Snake: <http://localhost:8000/snake-game.html>

## Technology

- HTML, CSS, and JavaScript
- Each game and its styles/scripts are contained in one HTML file.
- No frameworks, build step, third-party libraries, or remote assets.
- Browser local storage for preferences and best scores.

## Portfolio integrity

These are illustrative browser-game projects and requirements artifacts, not evidence of customer research or measured business results. Any future claims about users, outcomes, or AI capabilities should be added only when supported by verifiable work. Review new content for personal, employer, client, or confidential information before publishing.

## Repository contents

| File | Description |
| --- | --- |
| `memory-game.html` | Playable Memory game |
| `snake-game.html` | Playable Snake game |
| `PRD_new_dark_mode_feature.md` | Initial Memory theme requirements |
| `PRD_dark_theme.md` | Expanded Memory theme requirements |
| `PRD_snake_game.md` | Snake product requirements |
| `context.md` | Portfolio and project context for future contributors |
