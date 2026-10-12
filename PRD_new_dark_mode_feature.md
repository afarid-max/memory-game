# Product Requirements Document: Light and Dark Theme Toggle

## Overview

Add a user-controlled theme toggle to the Memory Game so players can switch between the existing light appearance and a new dark appearance. The selected theme should remain consistent as players use the game and return to it later.

## Background

The game currently uses a light page background, dark text, white panels and card fronts, and blue controls and card backs. Some of these colors are defined as CSS custom properties, while others are hard-coded. The game includes a responsive card grid, grid-size controls, statistics, a best-scores panel, and a completion dialog; all should remain legible and visually coherent in either theme.

## Goals

- Let players switch between light and dark themes at any time.
- Apply the chosen theme consistently across the entire game interface.
- Remember the player's choice across reloads in the same browser.
- Keep the game usable on mobile and with keyboard and assistive technology.
- Preserve gameplay, scores, and existing behavior when changing themes.

## Non-goals

- Redesigning the game or changing its gameplay, scoring, or layouts.
- Adding additional themes, custom color controls, or an automatic time-of-day schedule.
- Changing the saved best scores or how scores are ranked.

## Target users

Memory Game players who prefer a darker interface, want to reduce screen brightness, or simply want to choose the appearance that suits them.

## User experience

- Add a clearly named theme control near the game title or existing game controls.
- The control indicates the theme that will be activated, such as “Switch to dark mode” while light mode is active and “Switch to light mode” while dark mode is active.
- The game opens in light mode for first-time visitors, preserving the current default appearance.
- Activating the control immediately changes the complete interface without resetting the board, moves, timer, selected grid size, or scores.
- On later visits, restore the last explicitly selected theme.
- The theme control remains available and operable at all supported viewport sizes and while the completion dialog is displayed.

## Functional requirements

1. Provide two themes: light and dark.
2. Make the theme control operable by pointer and keyboard and expose its purpose and current action accessibly.
3. Apply theme colors to the page background, primary text, statistics panel, grid-size controls, card backs and fronts, best-scores panel, completion dialog, and interactive states, including hover and keyboard focus.
4. Maintain readable text and visible focus indicators in both themes. Preserve the existing card-flip animation and the visual distinction between face-down, face-up, and matched cards.
5. Persist the selected theme in browser-local storage and restore it on page load. If there is no saved choice, use light mode.
6. Changing themes must not alter game state or stored scores.
7. Keep the existing responsive layout and avoid introducing external dependencies.

## Acceptance criteria

- A new visitor sees the existing light theme.
- Selecting dark mode changes all game surfaces and text to the dark palette, including the active grid, statistics, score list, and completion dialog.
- Selecting light mode restores the light palette.
- Switching themes during an active game preserves the current cards, move count, timer, rating, and selected grid size.
- Reloading the page restores the most recently selected theme without affecting saved best scores.
- The theme control can be reached and activated using the keyboard, has an accessible name that describes its action, and displays a visible focus indicator.
- Text, controls, card states, and focus indicators remain distinguishable and readable in both themes on desktop and mobile-sized viewports.
- Existing game interactions, score saving, and the play-again flow continue to work in both themes.

## Design and implementation notes

- Reuse and extend the existing CSS custom-property theming approach rather than scattering theme-specific styles across components.
- Replace hard-coded surface and interaction colors where needed so the theme applies consistently.
- Represent the active theme on the document or main game container using a clear theme attribute or class.
- Use a dedicated local-storage key for the theme preference, separate from `memoryGameScores`.
- Respect reduced-motion preferences if theme-transition styling is introduced; theme switching must not interfere with the existing card-flip animation.

## Success measures

- Players can switch themes without interrupting or resetting a game.
- The selected appearance survives a page reload.
- Visual and keyboard checks confirm all game surfaces and interactive states work in both themes.
