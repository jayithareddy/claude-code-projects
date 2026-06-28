# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Running the project

Open `tic_tac_toe.html` directly in a browser — no build step, server, or dependencies required.

## Architecture

This is a single-file vanilla HTML/CSS/JS project. All game logic, styles, and markup live in `tic_tac_toe.html`.

**Game state** is held in three module-level variables:
- `board` — 9-element array (`null` | `'X'` | `'O'`), indexed 0–8 left-to-right, top-to-bottom
- `current` — whose turn it is (`'X'` or `'O'`)
- `over` — boolean that gates further moves
- `score` — `{X, O, D}` object that persists across `init()` calls (survives "New game")

**Win detection** (`checkWin`) iterates the eight `WINS` triplets and returns the winning indices or `null`.

**DOM pattern**: cells use `data-i` attributes as their index. State changes write to both `board[]` and the DOM simultaneously — there is no virtual DOM or reactive layer.

## Git workflow

Commit after every meaningful change with a descriptive message. Push to `origin/main` (GitHub: `jayithareddy/claude-code-projects`) so there is always a saved version to revert to.
