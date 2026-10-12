# Repository Context

## What this repository is

`memory-game-GHCP` contains a small, browser-based Memory (also known as Concentration) card game. The player flips cards to find matching pairs and can choose between a 4x4 board and a 6x6 board.

The game is implemented as a standalone HTML page in `memory-game.html`. Its CSS and JavaScript are embedded in that file, so it can be opened directly in a modern browser without installing packages, running a build, or connecting to a server.

## What the game does

- Shuffles and displays pairs of emoji cards.
- Supports 4x4 and 6x6 grids.
- Tracks moves and elapsed time and awards a star rating based on moves.
- Detects completed games and shows a results dialog with a Play Again action.
- Saves and displays up to five best scores in browser local storage.
- Supports card selection by mouse or keyboard and uses ARIA attributes for accessible interaction.
- Adjusts the layout for smaller screens.

## Project name

The repository is named `memory-game-GHCP`. The available project documentation describes the Memory Game, but does not define what the `GHCP` suffix stands for. Its expansion should not be assumed from the repository contents.

## Repository contents

- `memory-game.html` — the complete playable game, including styles and game logic.
- `README.md` — feature summary, instructions for playing, and local development guidance.
- `PRD_new_dark_mode_feature.md` — an earlier requirements document for a light/dark theme toggle.
- `context.md` — this overview of the repository.

## Technical characteristics

- Plain HTML, CSS, and JavaScript; no external dependencies.
- CSS Grid for the card layout and CSS transforms for card-flip animation.
- Browser local storage for high scores.
- The existing page is light themed. Some colors use CSS custom properties and other component surface colors are currently hard-coded.
- The README documents opening the HTML file directly or optionally serving the repository with Python's built-in HTTP server.

## Product direction

Keep the game easy to run and self-contained. Changes should preserve the existing gameplay, responsive layout, keyboard interaction, score persistence, and standalone browser usage unless a requirement explicitly calls for a behavior change.
