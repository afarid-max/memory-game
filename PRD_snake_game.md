# Product Requirements Document: Snake Game

## Summary

Add a standalone Snake game to the repository. The player steers a growing snake around a grid, eats apples to earn points, and avoids the board edges and the snake's own body. The game should run by opening one HTML file in a browser, with no external libraries or network dependencies.

## Background

The repository contains a standalone Memory game implemented with HTML, CSS, and JavaScript. Snake is a familiar arcade game that can be added alongside it while keeping the same easy-to-open, dependency-free format.

## Goals

- Provide a complete, playable Snake game in `snake-game.html`.
- Support keyboard play on desktop and touch-friendly controls on smaller screens.
- Make game state clear, with score, best score, ready, running, paused, and game-over states.
- Keep the game responsive, accessible, and usable with either light or dark appearance.
- Persist the best score and selected theme in the current browser.
- Preserve the existing Memory game and its data.

## Non-goals

- Multiplayer, online leaderboards, accounts, or network services.
- Configurable board dimensions, speed settings, or alternate game modes.
- Installing libraries, image assets, fonts, or other external dependencies.
- Changing the gameplay or score behavior of the Memory game.

## Target users

Players who want to play a familiar Snake game in a browser on desktop or mobile, without installing an application.

## User experience

- The page opens with a visible board, score, best score, theme control, and a clear Start game action.
- Starting or restarting begins a new round with the snake facing right.
- The player steers with arrow keys or W, A, S, D. Small screens also show directional buttons.
- The snake moves continuously, grows when it eats an apple, and earns 10 points per apple.
- The game ends when the snake hits a wall or itself. The final score remains visible, and the player can start again.
- The player can pause and resume with the Pause control or P/Space keyboard shortcut.
- Switching between light and dark themes does not reset or pause the game.

## Functional requirements

1. Render a 20-by-20 game board, snake, and food in the standalone HTML page.
2. Keep the snake moving at a steady interval and increase its speed as the score rises, with a lower bound on the interval.
3. Accept directional input from arrow keys and W, A, S, D, plus touch buttons at mobile viewport sizes.
4. Prevent an immediate 180-degree reversal into the snake's own body.
5. Place food only in unoccupied cells. Eating it grows the snake and adds 10 points.
6. End the round on wall or self collision and provide an action to start a fresh round.
7. Display the current score and the player's best score. Save a new best score in browser local storage.
8. Provide pause and resume controls. The keyboard shortcut P or Space must not interfere with activating buttons.
9. Provide light and dark themes, a keyboard-operable theme toggle, and persist the selected theme in a dedicated local-storage key.
10. Keep canvas rendering crisp on high-density displays and redraw when the board is resized or the theme changes.
11. Provide a live status message for important game-state changes and an accessible label for the game board.
12. Keep all gameplay code and styles in `snake-game.html`; do not require network access or third-party dependencies.

## Acceptance criteria

- Opening `snake-game.html` directly in a modern browser displays the board and controls without loading external resources.
- Starting a game moves the snake; directional inputs change its heading without allowing a direct reversal.
- Eating an apple increases the score by 10, lengthens the snake, and saves a new best score.
- Wall and self collisions end the round and permit a restart.
- Pause and resume work using both the button and supported keyboard shortcut.
- The direction controls are available on small screens, while keyboard play works on desktop.
- Theme changes recolor the page and board without changing gameplay state; the selected theme is restored after reload.
- The status and controls have accessible names and visible keyboard focus.
- The page remains playable at desktop and mobile viewport sizes and has no external runtime dependency.
- Existing Memory game files and saved data are unchanged.

## Implementation guidance

- Use semantic HTML, CSS custom properties for theme colors, and an HTML canvas for the grid and game pieces.
- Keep board coordinates in grid units and derive drawing dimensions from the canvas size.
- Use separate, dedicated local-storage keys for the Snake theme and best score.
- Keep game state transitions explicit so restarting, pausing, resuming, and collision handling remain predictable.
- Provide touch controls without removing keyboard support, and respect the user's reduced-motion preference for optional transitions.

## Validation and handoff

- Open the HTML file directly in a browser and verify initial rendering, start/restart, movement, scoring, pause/resume, theme switching, and game-over behavior.
- Verify that the board scales to a narrow viewport and that touch controls remain operable.
- Confirm the stored theme and best score survive a reload.
- Leave `snake-game.html` ready for the user to open and play.
