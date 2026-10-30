# Tap Dash — separated project

## Files

- `index.html` — page structure and game screens (menu, HUD, countdown, game-over).
- `css/style.css` — all visual styling and responsive layout.
- `js/game.js` — the original JavaScript runtime and game logic.

## Functional areas in the JavaScript

The supplied game was delivered as one minified, self-contained JavaScript bundle. It contains a bundled Three.js/WebGL engine and the Tap Dash game code inside one closure. The engine and game code share many private variables and classes, so splitting them into independent ES modules without a careful refactor would break their shared scope.

The game logic is therefore kept together in `js/game.js` to preserve behavior. Its main functional areas are:

1. **3D rendering and world** — bundled Three.js/WebGL implementation; creates and renders the 3D scene.
2. **Course generation** — deterministic seeded obstacle and coin generation (`Hs`).
3. **Player physics and movement** — runner state, jumping, gravity, collision/death and scoring (`Ws`).
4. **World/runner presentation** — world and player rendering (`Ys` and related classes).
5. **Game flow** — menu, countdown, playing, ending and game-over transitions (`vu`, `tr`, `g0`, `p0`).
6. **HUD and split-screen** — score/coin updates, player hints, death messages and responsive split-screen layout (`lo`, `l0`, `c0`).
7. **Player identity and local leaderboard** — nickname sanitizing/validation and saved top scores (`u0`, `d0`, `Jl`, `Gl`, `Zl`).
8. **Input** — pointer/touch controls and keyboard controls, including two-player controls (`oo`, `_0` and event listeners).
9. **Audio and mute** — sound state, sound effects and mute toggle (`yu`, `m0` and related audio helpers).

## Run

Open `index.html` through a local web server (recommended), rather than directly from `file://`, if your browser blocks WebGL or local script loading. No build step was added.

## Important

The JavaScript has been moved without changing its game logic. It remains minified because the source was a bundled production-style script; this is intentionally a structural split, not a risky rewrite. The next safe step is a staged refactor: first format and name the existing code, then extract modules one feature at a time with gameplay tests after each change.
# TapDash
# TapDash
