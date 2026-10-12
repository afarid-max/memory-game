# Product Requirements Document: Dark Theme for Memory Game

## Summary

Add an optional dark theme to the existing Memory Game. Players can switch between the current light appearance and a dark appearance without interrupting a game. The game should remember the selected theme in the current browser while preserving all existing gameplay and score behavior.

## Background

The repository contains a standalone browser game in `memory-game.html`, built with embedded HTML, CSS, and JavaScript. It supports 4x4 and 6x6 card grids, a timer, move counter, star rating, completion dialog, and best scores stored in browser local storage.

The page currently uses a light appearance. Its page and card colors partly use CSS custom properties, while several surfaces (including the statistics panel, score list, and completion dialog) have hard-coded light colors. A complete theme therefore needs to cover all game surfaces and relevant interaction states, not only the page background.

## Problem

Players cannot choose a darker appearance. Adding a theme control without addressing hard-coded component colors could leave bright panels in dark mode, reduce readability, or produce an inconsistent interface.

## Goals

- Let players switch explicitly between light and dark themes.
- Apply each theme consistently throughout the game.
- Preserve the current light appearance as the default for first-time visitors.
- Remember a player's chosen theme across page reloads in the same browser.
- Ensure theme changes do not reset or alter the game or saved scores.
- Keep the game standalone, responsive, and operable with keyboard and assistive technology.

## Non-goals

- Changing game rules, board sizes, card symbols, move rating, score ranking, or score format.
- Adding more than light and dark themes.
- Adding account-based or cross-device preferences, a settings page, or a scheduled automatic theme.
- Redesigning the game's layout or introducing third-party libraries.

## Users

Memory Game players who prefer a darker interface, want to reduce screen brightness, or want to choose the visual appearance of the game.

## User experience

- Add a visible theme toggle near the title or existing game controls.
- Use an accessible action label that describes the destination theme, such as “Switch to dark mode” in light mode and “Switch to light mode” in dark mode.
- Start in the existing light theme when no theme preference has been saved.
- Apply the selected theme immediately and keep the toggle available on small screens and while the completion dialog is shown.
- Keep the current board and its state unchanged when switching themes.

## Functional requirements

1. Provide light and dark themes.
2. The toggle must work with pointer and keyboard input, have an accessible name, and show a visible keyboard-focus indicator in both themes.
3. Theme colors must cover the page background and text; statistics panel; grid-size buttons and their hover, active, and focus states; card fronts and backs; score list; completion dialog; and other visible interactive states.
4. Preserve clear contrast between card faces, controls, text, and focus indicators in both themes. Do not impair the existing card-flip animation or distinguishability of face-down, face-up, and matched cards.
5. Persist the explicit selection in browser local storage using a dedicated key that does not overwrite or modify `memoryGameScores`.
6. Restore the saved theme when the page loads. If there is no valid saved theme preference, use the existing light theme.
7. Switching themes must not change the selected grid size, card arrangement, matched or flipped cards, move count, rating, timer, completion state, or saved scores.
8. Keep all existing game behavior working when either theme is active, including grid selection, card input, score saving/display, and Play Again.

## Acceptance criteria

- On a browser without a saved theme preference, the page looks and behaves as it does today in light mode.
- Activating the theme toggle changes every game surface and its applicable interactive states to a coherent dark palette; no light-only panel remains unintentionally bright.
- Activating the toggle again restores the light palette.
- Reloading the page restores the last explicitly selected theme.
- Switching themes mid-game leaves the board, cards, grid size, timer, moves, and rating unchanged.
- The theme preference is stored separately from the existing best-score data; saved scores remain intact before and after switching themes or reloading.
- The toggle is reachable and activatable by keyboard, has an action-oriented accessible name, and has a visible focus state.
- Text, buttons, card states, and focus indicators remain distinguishable at desktop and mobile viewport sizes.
- Existing game interactions and score behavior continue to work in both themes.
- The game remains a standalone HTML page with no new runtime or network dependency.

## Design and implementation guidance

- Extend the existing CSS custom-property approach with semantic theme variables for page background, surfaces, text, borders or shadows, primary controls, card faces, and focus states.
- Replace hard-coded surface and interaction colors where necessary so every affected component responds to the active theme.
- Expose the active theme on a root element using a clear attribute or class, with light mode as the fallback.
- Initialize the saved preference without rebuilding or resetting the game board.
- Use a dedicated local-storage key; do not change the existing `memoryGameScores` key or saved score schema.
- Avoid adding theme-transition effects that compete with card-flip animation. If theme transitions are added, respect reduced-motion preferences.

## Validation and handoff

Before handoff, verify both themes, reload persistence, toggling during an active game, score preservation, keyboard operation, and responsive layout. Confirm that grid changes, card matching, timer, completion dialog, and Play Again still behave normally in both themes.

After implementation and these checks, leave the game ready for the user to open and manually play in a browser. The user will perform the final visual/gameplay review.
