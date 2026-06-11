# Rubik's Rubrics

A stunning (if I do say so myself), self-contained 3D Rubik's Cube visualizer and solver. A scrambled cube appears,
then solves itself with smooth, eased layer-turn animations... and you control the show.

**▶ Live demo:** https://leereilly.net/rubiks-rubriks/

![](screenshot.webp)

![Rubik's Rubrics](https://img.shields.io/badge/three.js-r160-000?logo=three.js) ![No build step](https://img.shields.io/badge/build-none-2ea043) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## Features

- **Random scramble** — the cube shows up in a random state every time.
- **Animated solve** — watch it unscramble with buttery, eased quarter-turn animations.
- **Speed slider** — go from a slow crawl to turbo.
- **Timeline scrubber + transport** — scrub anywhere between *Scrambled* and *Solved*,
  step a single move back/forth, jump to either end, or play/pause.
- **GitHub contributions mode** — repaint the stickers as GitHub contribution-graph
  squares (those familiar greens).
- **Auto-rotate**, orbit (drag), and zoom (scroll) for a showcase feel.
- **Stunning rendering** — physically based glossy stickers, image-based reflections,
  soft contact shadows, and subtle bloom.

## How it works

The cube starts solved, then a random sequence of quarter turns scrambles it. The
solution is simply that sequence **reversed and inverted**, so every solve is valid by
construction — no solver library required. State is tracked as a small logical model
(each cubie's grid position + orientation quaternion), which keeps scrubbing
frame-perfect and drift-free.

## Running locally

It's a single `index.html` with no build step. Because it uses ES module imports from a
CDN, open it via a local server (not `file://`):

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Tech

[Three.js](https://threejs.org/) (WebGL) — `RoundedBoxGeometry`, `OrbitControls`,
`RoomEnvironment`, and `UnrealBloomPass`, all loaded from a CDN via an import map.

---

Made with ♥ and [GitHub Copilot](https://github.com/features/copilot) and Claude Opus 4.8 · max :metal:

## License

[MIT](LICENSE)
