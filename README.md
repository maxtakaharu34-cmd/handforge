# HandForge ✋

Gesture-driven 3D playground — control 3D objects with your bare hands, right in the browser.

**Live demo:** https://maxtakaharu34-cmd.github.io/handforge/

手のジェスチャーで3Dオブジェクトを操作できるWebアプリです。カメラに手をかざすだけで、オブジェクトを選択・掴む・投げることができます。

## How to use / 使い方

The app has three modes (switcher at the top center): **Play / Draw / Laser**.

### 🖐 Play mode
| Gesture | Action |
|---|---|
| 👉 Point (index finger) | Select / highlight an object（指差しで選択） |
| 🤏 Pinch (thumb + index) | Grab the object（ピンチで掴む） |
| ✊ Move while pinching | Move & rotate in 3D（動かして操作） |
| 🖐 Open hand | Release — object flies with inertia（開いてリリース） |
| 🖐💨 Open hand, move fast | Force push nearby objects（力場で押しのける） |
| ⭕ Circle an object with the index finger | Duplicate it（囲んで複製） |
| 🙌 Both hands | Manipulate two objects at once（両手同時操作） |

**Two-hand combos** — while one hand grabs an object, the other hand casts:
✌️ duplicate（複製）／ 👍 grow ×1.5（拡大）／ 🤙 shrink ×0.67（縮小）／ ✊ recolor（色替え）

### ✏️ Draw mode
Point with the index finger to draw glowing lines in 3D. Lines fade after 30 s; use **Clear Lines** to erase all.

### ⚡ Laser mode
Make a peace sign ✌️ to fire a glowing laser that knocks objects away. Hold the beam on the same target for about a second to shatter it.

### 🖼🎬 Media
Upload images or videos (button or drag & drop) — they appear as grabbable framed planes; videos loop as live textures.

## Tech stack

- [Three.js](https://threejs.org/) — 3D rendering, shadows, particles
- [MediaPipe Hands](https://developers.google.com/mediapipe) — real-time hand tracking (21 landmarks, 2 hands)
- Single HTML file, no build step, CDN only

## Run locally

Just open `index.html` in a browser (Chrome / Edge / Safari). Allow camera access when prompted. Internet connection is required for CDN assets.

## Features

- Mode-based UI (Play / Draw / Laser) with per-mode help hints
- Screenshot capture, zero-gravity toggle, and WebAudio sound effects (mutable)
- Glassmorphism dark UI with FPS counter, live gesture badge, camera preview
- Image & video upload as grabbable textured planes with glowing frames
- Two-hand combo gestures and circle-trace duplication
- Physics: inertia throws, gravity, floor bounce, soft bounds
- Particle bursts, ripples, and laser glow effects
- Distance-invariant pinch detection with landmark smoothing
- Graceful fallbacks: camera denied / not found / in use / CDN failure
