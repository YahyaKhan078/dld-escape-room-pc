<div align="center">

# 🔌 DLD Escape Room

### *"Freedom Is Just One Circuit Away"*

**A 2D educational puzzle game where you solve real Digital Logic Design problems to escape a sci-fi facility**

![Unity](https://img.shields.io/badge/Unity-6-black?style=flat-square&logo=unity)
![C#](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=csharp&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-Windows-blue?style=flat-square&logo=windows)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat-square)

[▶ Download & Play](#-download--play) · [Screenshots](#-screenshots) · [Features](#-features) · [Levels](#-levels)

</div>

---

## 🎮 About the Game

**DLD Escape Room** is a 2D educational puzzle game built in **Unity 6** for a university ICT project. You're trapped inside a sci-fi facility. The only way out? Build working digital logic circuits.

Each room presents a puzzle: construct a circuit using AND, OR, NOT, XOR, and NAND gates that satisfies a given truth table. Solve all 10 levels, and the exit door unlocks.

What makes it different from typical puzzle games: the circuit engine is **real**. It runs a genuine boolean logic simulation — students can solve each level in multiple valid ways, just like in real circuit design.

> Built to bridge the gap between DLD classroom theory and hands-on understanding. Designed to align with the **FSc Pre-Engineering** and **A-Level Computer Science** DLD curriculum.

---

## 📸 Screenshots

<!-- Add your screenshots here. Drag and drop images into the GitHub repo and paste the links below -->

| Main Menu | Puzzle Workspace |
|-----------|-----------------|
| ![Main Menu](screenshots/main-menu.png) | ![Puzzle](screenshots/level1-puzzle.png) |

| Hint System | Access Granted |
|-------------|----------------|
| ![Hints](screenshots/hint-system.png) | ![Win](screenshots/access-granted.png) |

| Exploration Map | Terminal Interaction |
|-----------------|---------------------|
| ![Map](screenshots/exploration-map.png) | ![NPC](screenshots/npc-dialogue.png) |

---

## ✨ Features

- **Custom Boolean Logic Engine** — Built from scratch in C#. Every gate is a live `Gate` object; `PropagateAll()` runs multi-pass chain resolution across the entire circuit in real time
- **Drag & Drop Gate Workspace** — Place AND, OR, NOT, XOR, NAND gates anywhere. Connect them with Bezier-curve wires that color live (cyan = HIGH, dark = LOW)
- **Real-Time Truth Table Validator** — Live OK/✗ feedback per row as you build. No waiting — the table updates with every wire you place
- **10 Progressive Levels** — From a single AND gate to 4-input sum-of-products circuits
- **Three Difficulty Modes** — Easy (3 levels), Medium (6 levels), Hard (all 10)
- **Hint System** — Animated popup with blur overlay providing guided clues
- **Exploration Map** — Top-down character movement between puzzle terminals with NPC dialogue
- **Cinematic Level Intros** — Fade-in / slide-up level name animations
- **Full Audio** — Sci-fi ambient tracks, wire-connect sounds, success/fail jingles
- **Gate Undo** — Ctrl+Z removes the last placed wire
- **Smooth Scene Transitions** — Fade effects managed by a `SceneTransitionManager` across 3 Unity scenes

---

## 🗺️ Levels

| Level | Name | DLD Concept | Logic Expression |
|-------|------|-------------|------------------|
| 1 | Airlock Override | AND Gate | `A AND B` |
| 2 | Mainframe Reboot | XOR Gate | `A XOR B` |
| 3 | Vault Breaker | Combined Gates | `(A OR B) AND NOT C` |
| 4 | Signal Filter | Inhibit Gate | `A AND NOT B` |
| 5 | Dual Trigger | XNOR | `NOT(A XOR B)` |
| 6 | Triple Lock | 3-input AND | `A AND B AND C` |
| 7 | Majority Vote | Sum of Products | `(AB)+(BC)+(AC)` |
| 8 | NAND Challenge | Universal Gate | NAND gates only |
| 9 | Priority System | OR Gate | `A OR B` |
| 10 | Final Override | 4-input SOP | Exactly 2 of 4 inputs HIGH |

---

## 🏗️ Technical Architecture

The game runs across **3 Unity scenes** connected by persistent singletons:

```
MainMenu Scene
    ↓  Player selects difficulty
ExplorationMap Scene
    ↓  Player walks to terminal, presses E
SampleScene (Puzzle)
    ↓  Player completes all levels
ExplorationMap Scene
    ↓  Exit door unlocks
YOU ESCAPED → Back to MainMenu
```

**Key systems:**

- `GateLogic.cs` — Core boolean evaluator; gates stored with unique IDs, connected via a wire list
- `DifficultyManager` — Singleton with `DontDestroyOnLoad`; persists chosen difficulty across scenes
- `UILineRenderer` — Custom `Graphic`-subclassed wire renderer using Bezier curve math
- `SceneTransitionManager` — Fade coroutines for seamless scene changes
- `ScriptableObjects` — Level data (expected truth tables, gate constraints) stored as assets

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Unity 6 (2D) | Game Engine |
| C# | Game Logic & Systems |
| TextMeshPro | UI Text Rendering |
| Kenney Tiny Dungeon | Tileset & Character Sprites |
| Freesound.org | Sound Effects & Music |
| Google Fonts (Orbitron, Share Tech Mono) | Typography |
| Git + GitHub | Version Control |

---

## ▶ Download & Play

1. Go to the [Releases](../../releases) tab
2. Download `DLD_EscapeRoom.zip`
3. Extract and run `DLD_EscapeRoom.exe`

**System Requirements:** Windows 10/11 · 4GB RAM · DirectX 11

---

## 🎮 How to Play

1. Select a difficulty from the main menu (Easy → Hard)
2. Walk your character to a terminal on the map and press **E**
3. In the puzzle workspace:
   - **Left-click** a gate in the sidebar to place it on the board
   - **Left-click** an output pin, then **left-click** an input pin to connect with a wire
   - Watch the **truth table** on the right — build until all rows show ✓
   - Press **TEST SYSTEM** to verify your circuit
   - Press **HINT** if you're stuck
4. Complete all terminals → the exit door unlocks → walk through to escape

---

## 👥 Team

| Member | Role |
|--------|------|
| **Yahya Khalid** | Lead Developer, Game Logic, Scene Architecture |
| **Zeeshan Nasim** | UI Design, Level Design |
| **Muhammad Hamdoon** | Boolean Engine, Testing |
| **Abeer Ihsan** | Audio Integration, Visual Polish |

---

## 🔭 Roadmap (v2.0)

- [ ] Android mobile build
- [ ] Sprite walk animations via Unity Animator
- [ ] Additional levels — flip-flops, multiplexers, shift registers
- [ ] In-game leaderboard with completion times
- [ ] Tutorial level for first-time players
- [ ] Multiplayer co-op wiring mode

---

## 📄 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

<div align="center">

**Built at GIK Institute · ICT Project · 2025**

*Yahya Khalid · Zeeshan Nasim · Muhammad Hamdoon · Abeer Ihsan*

</div>
