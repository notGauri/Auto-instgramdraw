<div align="center">

# 🎨 Auto Instagram Draw (InstaTrace)

**Turn any image into clean, sharp strokes and automatically draw it inside Instagram Draw — 100% offline on Android.**

[![Platform](https://img.shields.io/badge/Platform-Android%208.0%2B-3DDC84?style=for-the-badge&logo=android&logoColor=white)](#requirements)
[![Engine](https://img.shields.io/badge/Tracing%20Engine-Native%20Rust-000000?style=for-the-badge&logo=rust&logoColor=white)](#on-device-auto-draw-engine)
[![Status](https://img.shields.io/badge/Status-Free%20Early%20Access%20Beta-F59E0B?style=for-the-badge)](#how-to-get-the-app)
[![Stars](https://img.shields.io/github/stars/notGauri/Auto-instgramdraw?style=for-the-badge&color=A855F7)](https://github.com/notGauri/Auto-instgramdraw/stargazers)
[![Discord](https://img.shields.io/badge/Discord-Get%20Early%20Access-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/users/932075095374057514)

<br />

[Features](#-features) • [How It Works](#-how-it-works) • [Get Early Access](#-how-to-get-the-app) • [Setup Guide](#-installation--setup-guide) • [Privacy & Permissions](#-privacy--permissions) • [FAQ](#-troubleshooting--faq)

</div>

---

## ✨ Overview

**Auto Instagram Draw** is a lightweight Android drawing & outline-tracing assistant built for creators, sketch lovers, and anyone who wants clean, detailed artwork inside **Instagram Draw** (or any mobile drawing canvas).

Instead of relying on slow cloud AI tools that distort proportions or refuse images, everything runs **locally on your phone** using a custom **native Rust vectorization engine**. Open an image—or capture one straight off your screen—refine the strokes with a real vector eraser and offset cursor, and replay them smoothly inside your chosen draw area with full Play / Pause / Stop control.

> **Early Access Notice:** The app is currently in **Free Early Access (Beta)**. Source code and APK builds are maintained privately during beta testing. Star this repo to track updates, report bugs in **Issues**, and reach out on Discord to get the latest signed APK.

---

## 📸 Screenshots & Demo

> *(Drag and drop screenshots or a short screen-recording GIF of Auto Draw in action right here in GitHub's editor.)*

| Main Tracing Canvas | Auto Draw Tuning | Floating Overlay + Limit Box |
| :---: | :---: | :---: |
| *Add screenshot* | *Add screenshot* | *Add screenshot* |

---

## 🚀 Features

### ⚡ On-Device Auto Draw Engine (Powered by Rust)
- **Single-Pass Centerline Tracing:** Collapses ink lines into clean, sharp, continuous centerlines instead of messy dotted fragments or double-traced hollow outlines—specifically tuned for **anime, manga, and clean line art**.
- **Multiple Tracing Modes:**
  - **Anime / Line Art Mode:** Local adaptive thresholding + despeckling + skeletonization + angle-aware stroke walking.
  - **Colored Art / Photo Mode:** XDoG edge extraction for colored illustrations and photos.
  - **Shape / Outline Mode:** Built-in native VTracer vector mode for bold logos and flat shapes.
- **Live Tuning Sliders:** Adjust **Line Detail / Sensitivity**, **Noise Cleanup**, and **Smoothness** before committing strokes, with live stroke count and estimated draw time.
- **100% Offline & Uncensored:** No servers, no API keys, no rate limits, and zero image uploads.

### 📷 Floating Live Capture
- Trigger **Capture** straight from the floating control bar without leaving your current app.
- Frame any image on your screen with a draggable, resizable capture box.
- **Instant Auto Draw:** Captures the selected region, traces it in the background, saves it as your active drawing, and gets it ready to replay (with optional Auto-Play).
- **Capture & Draw:** Opens the cropped image directly on the locked canvas with auto-traced strokes loaded so you can manually draw extra details or clean up lines before replaying.

### ✏️ Precision Manual Tracing & Vector Eraser
- **Image Transform + Lock System:** Move, pinch-to-zoom, and rotate your reference image freely, then lock it in place to draw. Unlocking prompts to save your progress safely.
- **Distance Pointer (Offset Cursor):** Shifts the drawing tip away from your fingertip so your finger never blocks fine details. Customize distance (`20dp–150dp`), pointer size, style (*Crosshair*, *Circle*, *Dot + Circle*), and offset direction (*Above*, *Top-Left*, *Follow Movement*).
- **Real Vector Eraser (Not Pixel Painting):**
  - **Brush Erase (Partial):** Cleanly splits long strokes right where you swipe—so erased sections truly disappear from replay.
  - **Stroke Erase (Whole):** Swipe across stray dots or unwanted lines to remove entire strokes in one gesture.
- **Full Snapshot Undo / Redo:** Undo an entire erase swipe or an Auto Draw batch in a single tap.
- **Canvas Tools:** Brush size slider, color palette, restyle last stroke, and Light/Dark canvas toggle.

### 🎮 Floating Overlay & Safe Replay
- **Floating Control Bar:** Draggable overlay that sits cleanly over Instagram Draw with:
  - **Select Drawing** picker
  - **Play / Pause / Resume**
  - **Stop**
  - **Speed Presets** (`0.5x`, `1.0x`, `1.5x`, `2.0x`)
  - **Draw Area** selector
  - **Live Capture** button
- **Draw Limit Box:** Drag and resize an exact boundary box over Instagram's canvas. All strokes are strictly clipped inside the box so replay never accidentally taps Undo, Close, Back, or color buttons.
- **Interruption-Safe Pause:** If replay is interrupted by a notification or accidental touch, it pauses at the exact stroke index so you can hit **Resume** instead of starting over.

### 📂 Library, Visual Editor & Sharing
- **Drawing Library:** Save, rename, favorite (`★`), delete, and preview animated stroke playback right inside the app.
- **Fast Visual Editor:** Zoom/pan preview canvas, tap-to-select strokes, add/delete strokes, vector eraser, small-stroke cleanup slider, playback order scrubber (`0% → 100%`), and toggleable **JSON / SVG code view**.
- **Import & Export (JSON & SVG):** Back up your artwork, share clean outlines with friends, or import ready-made `.json` and `.svg` sketch packs in one tap.

---

## 🔄 How It Works

```text
1. Pick an Image (or use Floating Live Capture)
          │
          ▼
2. Position & Lock Image  ──►  Run Auto Draw (Rust Engine) OR Trace Manually
          │
          ▼
3. Clean Up with Vector Eraser & Save to Library
          │
          ▼
4. Open Instagram Draw  ──►  Set Draw Limit Box  ──►  Tap ▶ Play
