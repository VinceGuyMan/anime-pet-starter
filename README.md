# 🐾 Anime Pet Starter Pack (v0.1)

> **Tactical companion pet animation engine & interactive showcase.**  
> Procedural spring physics, landing squash & stretch, SVG path steering, and dynamic choreographies for 16-bit pixel-art desktop companions.

[![Live Demo](https://img.shields.io/badge/Demo-Live%20on%20GitHub%20Pages-2bf078?style=for-the-badge&logo=github)](https://vinceguyman.github.io/anime-pet-starter/)
[![Version](https://img.shields.io/badge/version-v0.1-0df0ff?style=for-the-badge)](https://github.com/VinceGuyMan/anime-pet-starter/releases/tag/v0.1)
[![License](https://img.shields.io/badge/license-MIT-yellow?style=for-the-badge)](LICENSE)

---

## 🎮 [Live Interactive Web Showcase](https://vinceguyman.github.io/anime-pet-starter/)

Try the live showcase directly in your browser: **[https://vinceguyman.github.io/anime-pet-starter/](https://vinceguyman.github.io/anime-pet-starter/)**

Features **Solid Snake** from the *Metal Gear Solid* pet ecosystem out of the box, with built-in support to **drag-and-drop or load ANY custom pet spritesheet**!

```
┌────────────────────────────────────────────────────────────────────────┐
│             ANIME PET STARTER PACK (Soliton Radar & CRT Grid)          │
├────────────────────────────────────────────────────────────────────────┤
│                                                                        │
│   [ ! ]  <-- Anime.js spring(1, 80, 10, 0) Elastic Alert Box           │
│    (•_•) <-- CSS steps(8) Frame Engine (Pixel-Crisp GPU Layer)         │
│   / | \  <-- Anime.js Squash & Stretch (scaleX: 1.28, scaleY: 0.72)    │
│    / \   <-- anime.path() Steering along Bezier Curves                 │
│                                                                        │
│   [📦 Box Drop]  [❗ Alert]  [🎯 SVG Patrol]  [📻 Codec]  [💥 CQC Hit]   │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 💡 The Core Concept: Dual-Layer Animation

Pixel art companion pets (such as those in **OpenPets / FROAM**, **Codex Pet v2**, and **Hermes**) typically have 8 fixed frames per action row. Hand-animating hundreds of transitional frames for every character is time-prohibitive.

This starter pack introduces a **hybrid architectural model**:

| Layer | Engine | Responsibility |
| :--- | :--- | :--- |
| **Micro Frame Cycling** | **CSS `@keyframes ... steps(8)`** | Integer-snapped, pixel-crisp GPU playback of the $192 \times 208\text{ px}$ spritesheet cells with zero subpixel blur or CPU drain. |
| **Macro / Spatial Motion** | **[Anime.js](https://github.com/juliangarnier/anime)** | Procedural squash-and-stretch, landing impacts, stride bobbing, elastic speech bubbles, and timeline choreographies. |

---

## ✨ Features Included in v0.1

1. **❗ The Classic MGS "!" Alert Sequence (`anime.timeline`)**:
   - Spring-loaded `[!]` alert bubble with elastic overshoot.
   - Startled vertical impulse hop with heavy landing squash (`scaleX: 1.28, scaleY: 0.72`).
   - Rapid 360° radar look-direction glance.
   - Dual-oscillator sound synthesis via the Web Audio API.

2. **📦 Cardboard Box Infiltration & Ambush**:
   - Cardboard box drops from the ceiling with bouncy physics (`easeOutBounce`).
   - Tiptoe stealth shuffle with rotational wobble (`rotate: [-4deg, 4deg]`).
   - Box springs open when the pet salutes.

3. **🎯 SVG Vector Patrol Navigation (`anime.path`)**:
   - Steers the companion smoothly along Bézier curves across the screen.
   - Computes path tangents in real-time to mirror the sprite when turning around.

4. **📻 Codec Radio Transmission**:
   - Codec transceiver HUD slides in with spring damping.
   - Frequency tuner and character portrait.
   - Dialogue typewriter and synthesized incoming call chimes.

5. **💥 CQC Impact & Particle Burst (`anime.stagger`)**:
   - Screen shake impulse with decaying amplitude.
   - 16 radial burst particles staggered outward.
   - Knockback into the pet's defeat pose (Row 5 `failed`).

6. **📁 Custom Spritesheet Dropzone**:
   - Click **"Load Custom Pet"** in the top bar to drop in any local spritesheet (`PNG` or `WEBP`).
   - Immediately tests all animations and physics on your own character!

7. **🖱️ Click-to-Move Spring Waypoints**:
   - Click anywhere on the tactical floor to send the pet running to that waypoint with auto-facing and distance-based spring physics.

---

## 📐 Spritesheet Specification Standard

This starter pack follows the standard **Codex Pet v2 / OpenPets** 11-row layout ($1536 \times 2288\text{ px}$, $192 \times 208\text{ px}$ per cell, 8 columns $\times$ 11 rows):

| Row | State | Frames | Purpose |
| :---: | :--- | :---: | :--- |
| **0** | `idle` | 8 | Gentle idle breathing / stance |
| **1** | `running-right` | 8 | Smooth directional run / glide moving right |
| **2** | `running-left` | 8 | Smooth directional run / glide moving left |
| **3** | `waving` | 8 | Greeting, alert wave, or salute |
| **4** | `jumping` | 8 | Vertical leap or victory celebration |
| **5** | `failed` | 8 | Defeat, knockback, or game-over pose |
| **6** | `waiting` | 8 | Waiting for input, sitting, or crouch |
| **7** | `running` | 8 | Turbo sprint or dash |
| **8** | `review` | 8 | Transceiver call, reading map, or inspecting prop |
| **9** | `look-0-7` | 8 | Clockwise look: North ($0^\circ$) $\rightarrow$ Southeast ($157.5^\circ$) |
| **10** | `look-8-15` | 8 | Clockwise look: South ($180^\circ$) $\rightarrow$ North-Northwest ($337.5^\circ$) |

---

## 🚀 Quick Start (Local)

No Node.js or build steps required—it runs directly in any modern web browser:

```bash
git clone https://github.com/VinceGuyMan/anime-pet-starter.git
cd anime-pet-starter
open index.html   # On macOS, or open index.html in any browser
```

---

## 📦 What's in the Box?

```
anime-pet-starter/
├── index.html                 # Interactive showcase & web playground
├── anime.min.js               # Vendored Anime.js v3.2.2 library
├── spritesheet.png            # Solid Snake 16-bit spritesheet (1536x2288)
├── spritesheet.webp           # Lossless WebP spritesheet
├── pet.json                   # Solid Snake manifest (Codex Pet v2)
├── template-pet.json          # Starter manifest template for custom pets
├── LICENSE                    # MIT License
└── .github/
    └── workflows/
        └── deploy-pages.yml   # Automatic GitHub Pages deployment
```

---

## 🤝 Adding Your Own Pet

1. Replace `spritesheet.png` with your pet's $1536 \times 2288\text{ px}$ spritesheet.
2. Edit `template-pet.json` with your pet's `id`, `displayName`, and `description`.
3. Open `index.html` to preview your character in action!

---

## ⚖️ Fan Project Disclaimer & Credits

* Solid Snake, Metal Gear Solid, and related characters, names, and trademarks belong to **Konami Digital Entertainment**.
* This is an unofficial, non-commercial fan-made starter pack created for open-source desktop companion experimentation.
* Repository documentation and integration code are offered under the [MIT License](LICENSE).
