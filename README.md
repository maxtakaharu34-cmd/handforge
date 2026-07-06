# HandForge ✋

Gesture-driven 3D playground — control 3D objects with your bare hands, right in the browser.

**Live demo:** https://maxtakaharu34-cmd.github.io/handforge/

手のジェスチャーで3Dオブジェクトを操作できるWebアプリです。カメラに手をかざすだけで、オブジェクトを選択・掴む・投げることができます。

## How to use / 使い方

| Gesture | Action |
|---|---|
| 👉 Point (index finger) | Select / highlight an object（指差しで選択） |
| 🤏 Pinch (thumb + index) | Grab the object（ピンチで掴む） |
| ✊ Move while pinching | Move & rotate in 3D（動かして操作） |
| 🖐 Open hand | Release — object flies with inertia（開いてリリース、慣性で飛ぶ） |
| 🙌 Both hands | Manipulate two objects at once（両手同時操作） |

## Tech stack

- [Three.js](https://threejs.org/) — 3D rendering, shadows, particles
- [MediaPipe Hands](https://developers.google.com/mediapipe) — real-time hand tracking (21 landmarks, 2 hands)
- Single HTML file, no build step, CDN only

## Run locally

Just open `index.html` in a browser (Chrome / Edge / Safari). Allow camera access when prompted. Internet connection is required for CDN assets.

## Features

- Glassmorphism dark UI with FPS counter and camera preview
- 6–8 colorful objects with varied materials (Standard / Phong)
- Physics: inertia throws, gravity, floor bounce, soft bounds
- Particle bursts on grab / release, emissive glow feedback
- Distance-invariant pinch detection with landmark smoothing
- Graceful fallbacks: camera denied / not found / CDN failure
