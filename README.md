# Cappella degli Scrovegni – 3D Interactive Experience

![Award](https://img.shields.io/badge/🥇 1st Place-To Digital Competence 4.0 \(Veneto\)-orange)

## Project Overview

This repository contains the source code for a browser‑based 3D exploration of the **Cappella degli Scrovegni** (Scrovegni Chapel) in Padua, Italy. I built the application in **March 2022**, during the third year of liceo, as lead developer together with [@tommasomoro8](https://github.com/tommasomoro8).

The project earned **1st place** in the regional competition **“To Digital Competence 4.0”** (Veneto Region) organised by MIM / USR Veneto / AICA, later showcased at the national *Job & Orienta 2023* fair. <sup>[USR Veneto ranking PDF](https://istruzioneveneto.gov.it/wp-content/uploads/2023/06/m_pi.AOODRVE.REGISTRO-UFFICIALEU.0015352.09-06-2023.pdf)</sup> <sup>[School press release](https://liceoduca.edu.it/2023/12/03/concorso-to-digital-competence-4-0/)</sup>

As part of the award, every member of the team received a complimentary **ICDL (ECDL) Full Standard certification** from AICA.

## Demo

> **[Live Demo](https://cappelladegliscrovegni.netlify.app/) – explore the chapel directly in your browser.** Clone the repo and open `index.html` with a local server (see *Getting Started* below) to explore the chapel interactively.

## Key Features

| Feature                  | Description                                                                    |
| ------------------------ | ------------------------------------------------------------------------------ |
| **Immersive 3D model**   | High‑fidelity Collada model (`.dae`) of the chapel with PBR textures.          |
| **Interactive hotspots** | Clickable points of interest reveal details about specific frescoes.           |
| **Custom camera paths**  | Smooth tweened transitions (Tween.js) between curated viewpoints.              |
| **Multilingual UI**      | Italian 🇮🇹 and English 🇬🇧 localisation.                                    |
| **Audio narration**      | Contextual audio tracks for each artwork (separate Italian & English folders). |
| **Dark / Light mode**    | Toggleable theme for optimal visibility.                                       |
| **Responsive layout**    | Works on desktop and mobile; OrbitControls adapt to touch.                     |

## Technology Stack

| Layer              | Tool / Library                                   | Role                                            |
| ------------------ | ------------------------------------------------ | ----------------------------------------------- |
| **3D Rendering**   | [Three.js](https://threejs.org/)                 | Scene graph, materials, shaders, render loop    |
| **Runtime**        | WebGL 2                                          | Hardware‑accelerated graphics in the browser    |
| **Model Loader**   | `ColladaLoader`                                  | Imports the chapel `.dae` model                 |
| **Camera Control** | `OrbitControls` + custom easing                  | User navigation and scripted fly‑throughs       |
| **Animation**      | [Tween.js](https://github.com/tweenjs/tween.js/) | Smooth interpolation for camera + UI            |
| **UI / State**     | Vanilla JS, HTML5, CSS3                          | Light‑weight UI, language toggle, modal dialogs |
| **Build tooling**  | None (plain ES modules)                          | Zero‑config static hosting                      |

## Folder Structure

```
├─ /audio/            # Narration tracks (it, en)
├─ /cubemap/          # HDR skybox textures
├─ /img/              # UI and reference images
├─ /render/           # Texture maps for the 3D model
├─ /system/           # Icons, loader GIF, etc.
├─ /scripts/
│   ├─ app.js         # Bootstrap + main loop
│   ├─ render.js      # Three.js scene setup
│   ├─ data.js        # Hotspot + localisation data
│   ├─ home.js        # Landing‑page logic
│   ├─ form.js        # Feedback submission
│   └─ analytics.js   # Basic usage tracking
└─ index.html
```

## What I Learned

1. **Three.js deep‑dive** – scene graph management, physically based lighting, shadow optimisation, custom shader tweaks.
2. **Performance tuning for WebGL** – texture atlas creation, model decimation, frustum culling to keep >60 FPS on mid‑range phones.
3. **Responsive 3D UX** – translating desktop orbit controls to touch gestures and adaptive GUI scaling.
4. **Internationalisation** – building a locale‑driven content layer (JSON) for text + audio assets.
5. **Project leadership** – planning sprints, Git workflow, delegating asset tasks to modelling and content teammates.
6. **Competition delivery** – preparing a live demo, pitch deck, and documentation that convinced a mixed technical/non‑technical jury.

## Awards

| Year | Competition                                   | Category                   | Result                          | Role           |
| ---- | --------------------------------------------- | -------------------------- | ------------------------------- | -------------- |
| 2023 | **To Digital Competence 4.0** – Veneto Region | Triennio (Upper Secondary) | 🥇 1st place – “Digitalizzando” | Lead developer |

*Official ranking: USR Veneto Prot. 15352/09‑06‑2023*
*Prize:* Complimentary ICDL Full Standard certification for the entire class.

## Getting Started

1. **Clone the repo**

   ```bash
   git clone https://github.com/IvanLomaka/cappelladegliscrovegni.git
   cd cappelladegliscrovegni
   ```
2. **Run a local server** (e.g. `python -m http.server` or VS Code “Live Server”).
3. Navigate to `http://localhost:8000` and start exploring.

## License

This project was created strictly for educational purposes. All rights to the artworks and photographic material belong to their respective owners. Please contact the maintainers for any usage beyond personal or academic viewing.

---
Created by Ivan & Tommaso | Liceo Duca degli Abruzzi | March 2022