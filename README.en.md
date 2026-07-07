# 🧲 Magnetic Fields

> Vector-field magnetic simulator built with HTML5 Canvas

Drag bar magnets with N and S poles into position. Thousands of fine iron-filing particles align and flow along the magnetic field lines in real time, painting the beautiful hyperbolic patterns of dipole field interactions.

[🇰🇷 한국어](./README.md) · [🇺🇸 English (default)](#)

---

## 🎬 Live Demo

> **👉 [https://magnetic-fields.vercel.app/](https://magnetic-fields.vercel.app/)** — Run instantly in any modern browser

| | |
|---|---|
| ![Live](https://img.shields.io/badge/Live-Demo-7C3AED?style=for-the-badge&logo=vercel&logoColor=white) | [![Repo](https://img.shields.io/badge/GitHub-sigco3111%2Fmagnetic--fields-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/sigco3111/magnetic-fields) |
| ![Status](https://img.shields.io/badge/Status-Live-22C55E?style=flat-square) | ![Stack](https://img.shields.io/badge/Stack-Vanilla_JS-F7DF1E?style=flat-square&logo=javascript&logoColor=black) |
| ![License](https://img.shields.io/badge/License-MIT-F1C40F?style=flat-square) | ![Deps](https://img.shields.io/badge/Dependencies-0-9CA3AF?style=flat-square) |

### ⚡ Quick Start
1. Click the demo link above → page opens in browser
2. **Press A** — spawn a new magnet near the screen center
3. **Drag with mouse** — reposition any magnet
4. **Press R** — rotate the selected magnet 15° (Shift+R = reverse)
5. **Press +/−** — adjust particle count in steps of 500 (500–8,000)

---

## 🤖 Generation Info

This project's code was generated automatically using the model and prompt below.

| Item | Value |
|---|---|
| **Model** | MiniMax-M3 (MiniMax) |
| **Environment** | OpenCode CLI |
| **Repository** | [`sigco3111/magnetic-fields`](https://github.com/sigco3111/magnetic-fields) |
| **License** | MIT |
| **Dependencies** | None (Vanilla JS, single HTML) |

### 📝 Prompt Used (Original)

```
Build a screen where the user can drag multiple bar magnets with N and S poles
into position. Around them, thousands of fine iron-filing particles should align
and flow in real time along magnetic field lines, visualized as beautiful
hyperbolic patterns.
Implementation Advice: Use HTML5 Canvas. The physics is Vector Field
calculation. For each particle, calculate the force vector sum from all poles
(N repel, S attract). Rotate the particle sprite to align with the field
vector. Package all dependencies in a single HTML file.
```

---

## ✨ Features

- 🧲 **Draggable Magnet System** — bar magnets with N (red) and S (blue) poles — place, rotate, delete
- ✨ **Thousands of Particles** — default 3,500; adjustable from 500 to 8,000
- 🌊 **Vector Field Simulation** — each particle sums forces from every pole and aligns with the field
- 🔄 **Live Rotation Alignment** — particle sprites rotate to match the local field vector
- 🎨 **Hyperbolic Patterns** — N↔S pole interactions emerge as beautiful curved flux lines
- 📦 **Single HTML** — 26 KB, no build step, opens anywhere
- 🌐 **L Key Language Toggle** — instantly switch UI labels between Korean and English

---

## 🚀 Quick Start

### Method 1: Open directly in browser (simplest)
```bash
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

### Method 2: Local server (recommended)
```bash
python3 -m http.server 8000
# → http://localhost:8000
```

### Method 3: Live Demo
Open the Vercel alias URL above — no install required.

---

## 🎮 Controls

| Input | Effect |
|---|---|
| **A key** | Spawn a new magnet near the center |
| **Mouse drag** | Move a magnet |
| **Right-click drag** | Rotate a magnet |
| **R key** | Rotate selected magnet by 15° (Shift+R = -15°) |
| **Delete / Backspace** | Delete the selected magnet |
| **C key** | Clear all magnets |
| **Space** | Pause / resume |
| **+/− keys** | Adjust particle count in steps of 500 (500–8,000) |
| **T key** | Toggle trail effect |
| **L key** | Toggle UI language between Korean and English |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Rendering** | HTML5 Canvas 2D Context (`desynchronized: true`) |
| **Physics** | Custom vector field calculation (`Σ F = K·q·(±)/r^α`) |
| **Loop** | `requestAnimationFrame` |
| **DPR** | Up to 2× for high-DPI displays |
| **Dependencies** | None (Vanilla JS) |

### Key Constants

| Constant | Value | Meaning |
|---|---|---|
| `PARTICLE_COUNT` | 3,500 | Default particle count |
| `MAX_PARTICLES` | 8,000 | Max particle count |
| `MIN_PARTICLES` | 500 | Min particle count |
| `MAX_MAGNETS` | 8 | Max magnets on screen |
| `MAGNET_LEN` | 120 px | Magnet length |
| `MAGNET_WIDTH` | 22 px | Magnet thickness |
| `K` | 1,800 | Field strength coefficient |
| `ALPHA` | 1.5 | Distance falloff exponent (1/r^α) |
| `EPS²` | 900 | Softening (squared unit distance) |
| `DAMPING` | 0.90 | Particle velocity damping |
| `BASE_SPEED` | 1.4 | Tangential drift speed |

---

## 📂 Project Structure

```
magnetic-fields/
├── index.html      # Single HTML containing all code (~26KB)
├── README.md       # 한국어 (default)
├── README.en.md    # English
└── LICENSE         # MIT
```

---

## 🎨 Design Decisions

Five choices made during brainstorming:

| Decision Point | Choice | Rationale |
|---|---|---|
| **Physics Model** | Direct vector field summation (`Σ F`) | Hyperbolic field lines emerge naturally |
| **Distance Falloff** | `1/r^1.5` (ALPHA=1.5) | Reaches farther than pure 1/r²; visually balanced |
| **Softening** | `EPS² = 900` (~30 px²) | Prevents divergence at pole surface |
| **Rotation Alignment** | Sprite rotates with local field vector | Faithfully models real iron-filing self-alignment |
| **Single HTML + Zero Dependencies** | Pure Canvas + Vanilla JS | Runs anywhere instantly, no build step |

### Customization

Tune the `CONFIG` object at the top of `index.html` to alter the physical feel and visuals:

```js
const CONFIG = Object.freeze({
  PARTICLE_COUNT:  3500,   // Default particle count (perf tradeoff)
  K:               1800,   // Field strength (higher = more violent near poles)
  ALPHA:           1.5,    // Distance falloff exponent (higher = local only)
  DAMPING:         0.90,   // Particle damping (1.0 = no damping)
  BASE_SPEED:      1.4,    // Tangential drift speed
  FADE_ALPHA:      0.10,   // Trail fade intensity (lower = longer tails)
  // ... more options documented in source
});
```

Advanced: setting `EPS²` near 0 produces explosive patterns at pole surfaces; setting it very high yields smooth gradient fields.

---

## 📜 License

MIT © 2026 sigco3111

---

## 🙏 Acknowledgments

This project was generated by the **MiniMax-M3** model in the OpenCode CLI environment. Prompt engineering and design decisions were made directly by the repository owner.