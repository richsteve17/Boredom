# Boredom

A cure for it.

## 🎮 NEON DODGE

A juicy, zero-dependency neon arcade survival game. One HTML file, no build
step, runs in any modern browser — desktop or mobile.

### Play

Open `index.html` in a browser. That's the whole install.

Or serve it locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

### How to play

- **Move** your glowing orb with the mouse, touch, **WASD**, or **arrow keys**.
- 🟢 **Pickups** — swallow them for points. Grab 5 in a row to bump your score
  multiplier (up to x9). Let one expire and your streak resets.
- 🔴 **Hunters** — they spawn from the edges and home in on you. Touch one and
  it's over. They get faster the longer you survive.
- 🟣 **Shockwaves** — rare. Grab one to detonate a blast that clears every
  hunter nearby.
- **Pause** with `P` or `Esc`. `Space` / `Enter` starts or restarts.

Your best score is saved locally. How long can you last?

### Features

- Particle bursts, motion-blur trails, screen shake, and bloom glow
- Smoothly scaling difficulty
- Mouse, touch, and keyboard controls
- Persistent high score via `localStorage`
- Single self-contained file, ~600 lines, no dependencies
