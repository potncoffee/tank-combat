# Tank Combat

A single-file browser remake of games 1–14 of Atari's **Combat** (1977, CX2601) —
the tank family: Tank, Tank-Pong, Invisible Tank, and Invisible Tank-Pong.

**▶ Play it here: https://potncoffee.github.io/tank-combat/**

No installs, no dependencies, no build step. One HTML file.

## The 14 games

Reproduced exactly from the original 1977 manual (C011402-01):

| # | Family | Field | Missiles / Scoring |
|---|--------|-------|--------------------|
| 1 | Tank | Open | Guided |
| 2 | Tank | Easy maze | Guided |
| 3 | Tank | Easy maze | Straight |
| 4 | Tank | Complex maze | Guided |
| 5 | Tank | Complex maze | Straight |
| 6 | Tank-Pong | Easy maze | Direct or billiard |
| 7 | Tank-Pong | Complex maze | Direct or billiard |
| 8 | Tank-Pong | Open | Billiard only |
| 9 | Tank-Pong | Easy maze | Billiard only |
| 10 | Invisible Tank | Open | Guided |
| 11 | Invisible Tank | Easy maze | Guided |
| 12 | Invisible Tank-Pong | Easy maze | Direct or billiard |
| 13 | Invisible Tank-Pong | Open | Billiard only |
| 14 | Invisible Tank-Pong | Easy maze | Billiard only |

**Tank-Pong** missiles ricochet off walls; *billiard-only* games require at
least one bounce before a hit scores, and your own ricochet can hit you but
never scores against you. **Invisible** tanks (both of them, yours included)
appear only when firing, when hit, or when bumping a wall.

## Controls

- **Arrows** or **WASD** (pick on the menu) — left/right rotate in place,
  up drives forward, down reverses
- **Space** — fire; in guided-missile games, left/right steer the shell in flight
- **Esc** — back to menu

**Two-player** (set OPPONENT to 2 PLAYER on the menu, one keyboard):

- **Player 1** — WASD to drive, **Space** to fire
- **Player 2** — Arrows to drive, **Enter** to fire

Solo against an AI tank (difficulty 1–5) or couch versus, as in 1977.
Rounds last 2:16, most hits wins.

## Faithful vs. modernized

Faithful: the game matrix, 16 tank headings, rotate-in-place, guided missile
steering, billiard scoring rules, invisibility flashes, spin-out on hit, the
2:16 clock, couch two-player. Modernized: the AI opponent, SNES-grade
pixel-art sprites, six selectable palettes (two neon), reverse gear, and
anti-farming rules (post-hit grace period, deadlock-free tank collisions,
AI stand-off range).

## Tinkering

Everything is in `index.html`, deliberately hackable:

- **Wall looks** live in the `WALL_STYLES` registry; palettes reference a
  style by name. Add a function, point a palette at it.
- **Palettes** are five-shade arrays; sprites recolor automatically via
  palette-index swap, the authentic 16-bit method.
- **Physics** are named constants at the top of the script.
- Jump straight into a game with a URL hash:
  [`#game=10&pal=1&diff=4`](https://potncoffee.github.io/tank-combat/#game=10&pal=1&diff=4)

## License

[MIT](LICENSE)
