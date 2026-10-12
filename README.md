# Browser Games

A collection of responsive, standalone childhood games built with HTML, CSS, and JavaScript. Open a game's HTML file directly in a modern browser to play; no installation or external dependencies are required.

## Games

### Memory Game

Play the classic Concentration game by finding matching pairs.

- Choose a 4x4 or 6x6 card grid
- Track moves, time, and star rating
- Save best scores in the browser
- Flip cards with a mouse, touch, or keyboard
- Switch between light and dark themes

**Play:** Open [`memory-game.html`](memory-game.html).

### Snake

Guide the snake to eat apples, grow longer, and avoid the walls and its own tail.

- Keyboard controls: arrow keys or W, A, S, D
- Touch direction buttons on small screens
- Score and locally saved best score
- Pause and resume with the button, P, or Space
- Switch between light and dark themes

**Play:** Open [`snake-game.html`](snake-game.html).

**Snake product requirements:** [`PRD_snake_game.md`](PRD_snake_game.md).

## Run the games

The simplest way to play is to open either HTML file in your browser. Alternatively, from this folder, start a local web server:

```bash
python3 -m http.server 8000
```

Then open:

- Memory Game: <http://localhost:8000/memory-game.html>
- Snake: <http://localhost:8000/snake-game.html>

## Project details

- Each game is a self-contained HTML file with embedded CSS and JavaScript.
- No third-party libraries, build tools, or network access are required.
- Preferences and personal best scores are stored locally in the browser.

## Contributing

1. Clone the repository.
2. Open a game HTML file directly, or use the local server instructions above.
3. Keep games self-contained and test them in a browser at desktop and mobile sizes.