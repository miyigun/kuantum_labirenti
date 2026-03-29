[🇹🇷 Click here for Turkish](README.tr.md)

# Kuantum Labirenti (Quantum Maze)

This repository contains a **browser-based, interactive 3D puzzle/game** built on **graph theory** and real-time decision making.

You play a 25-level “crisis management simulation” where you must travel from the **start node (A)** to the **target node (G)** by selecting connected nodes on a 3D graph — while managing **time** and **resource cost** constraints.  
A key mechanic is **cost fluctuation**: edge costs can change after each move, so the best route is not always the shortest one.

---

## Features

### 1. 3D Graph Labyrinth (Three.js)
- Fully interactive **3D scene**
- Drag to rotate the labyrinth
- Mouse wheel / pinch to zoom
- Click/tap nodes to move between them

### 2. 25 Levels (Procedural Generation)
- **25 stages** (`1 / 25` in UI)
- Each level generates a new graph:
  - Increasing node count as level rises
  - Difficulty scales via time & cost constraints

### 3. Strategy: Cost vs. Efficiency
- **Edge costs** represent resource consumption
- Costs can **fluctuate after each move**
- Winning requires balancing:
  - total cost (must stay under limit)
  - time remaining (countdown timer)

### 4. Score System & Results
- Score is computed from:
  - remaining cost budget
  - remaining time
- Win / fail modals with actions:
  - retry level
  - reset system (reload)

### 5. Audio + Music Toggle
- Simple synth SFX via **Web Audio API** (step / win / fail)
- Background music from `mp3/music.mp3`
- Music on/off toggle button

### 6. Mobile/Device UX
- Orientation warning: designed for **landscape mode**
- Touch support (tap to select nodes, pinch to zoom)

---

## Project Structure

- `index.html` — entire application (UI + styles + game logic + Three.js scene)
- `mp3/music.mp3` — background music

External libraries loaded via CDN:
- jQuery
- Three.js (r128)

---

## Getting Started

### Run locally
1. Clone the repository:
   ```bash
   git clone https://github.com/miyigun/kuantum_labirenti.git
   ```
2. Enter the folder:
   ```bash
   cd kuantum_labirenti
   ```
3. Start a local server (recommended):
   ```bash
   python -m http.server 8000
   ```
4. Open:
   - `http://localhost:8000`

> Note: Running via a local server avoids browser restrictions around local file access and provides more consistent audio behavior.

---

## 🛠️ Technologies Used
- HTML (single-page)
- JavaScript (inline)
- Three.js (3D rendering)
- jQuery (UI/event helpers)
- Web Audio API (sound effects)
- Audio file playback (`mp3/music.mp3`)

---

## 📌 Notes
- **Goal:** reach the target node **G** starting from **A**.
- **Lose conditions:**
  - time reaches zero
  - cost exceeds the level cost limit
- Costs can change after each step, so “optimal” paths are dynamic.
- The app is designed for **landscape orientation** on mobile devices.

---

## 📜 License
MIT License (see `LICENSE`).