## Aviso sobre a origem e as contribuições

Este repositório contém uma versão aprimorada do **Liastra Mission**, projeto desenvolvido pela equipe **LIASTRA (Campinas)**, da qual fiz parte, e submetido oficialmente ao **NASA Space Apps Challenge 2026**.

Após minha participação no desenvolvimento e na submissão oficial, dei continuidade ao projeto de forma independente, implementando melhorias, adaptações e novas funcionalidades, com foco na experiência do usuário, na evolução técnica e no potencial educacional do simulador.

**Repositório oficial submetido ao hackathon:**
https://github.com/aniramanin/missao-liastra

Esta versão representa a continuidade do meu trabalho no projeto e **não constitui uma nova submissão ao hackathon**. O desenvolvimento original é fruto da colaboração de toda a equipe LIASTRA, enquanto as evoluções posteriores deste repositório correspondem às minhas contribuições individuais.

---

# Aerospace Innovation Center · Liastra Mission

A 3D space-mission simulator for all ages, built by the **LIASTRA team** (Campinas hub) for the **NASA Space Apps Challenge 2026**.
Wake up at a Mars base, walk on the Moon, float inside a copy of the Space Station, and complete real missions with real NASA data.

**Play (no login, no download):** https://babidoo.github.io/NASA-Space-App-2026/

## What it is
- Static web app: one `index.html` plus a local `vendor/` folder (Three.js r128). No backend, no build step, works offline except for the live NASA data.
- **14 missions** across Mars, the Moon and the ISS, each based on a real event (CHAPEA, Opportunity's dust storm, Apollo 13's CO₂ filter, Artemis, the ISS daily routine, EVAs and cargo capture), plus a free-play **Survival** mode per world.
- Energy, air, water, food and radiation model; space agriculture with 6 crops; random events that end with a real fact and its source.

## Training features
- **Flight evaluation:** every flight is graded on safety (radiation), resources, procedure and knowledge, with a debrief that points at your weakest area.
- **Learning objective** before each mission and a **mini-quiz** during it, tied to the real fact of that step. Correct answers give a bonus, wrong ones cost a little, and the result counts in the grade.
- **Guided tutorial** (about 2 minutes, runs once) that teaches look, move, interact, tablet and the first task.
- **Career ranks:** XP accumulates across flights (Recruit → Trainee → Specialist → Pilot → Mission Commander → Space Legend). First clears pay more than replays, so the ladder rewards new missions.
- **Daily challenge:** a Survival run built from a real DONKI space-weather window. Everyone who plays on the same day faces the same storms. Completing it pays bonus XP and builds a daily streak.

## Real NASA data
- Solar storms follow the real Sun: coronal mass ejections from **NASA DONKI** (`api.nasa.gov/DONKI/CME`). If the API is unreachable, the game falls back to a real archive embedded in the page and says so on screen.
- Mars–Earth communication delay is computed in the browser from JPL approximate orbital elements.
- Sources: NASA DONKI (CCMC), NASA Open APIs, NASA/JPL, NASA OSDR, NASA Science; Hassler et al. 2014 (Curiosity RAD); Zhang et al. 2020 (Chang'e 4); Paul et al. 2022; Garrett-Bakelman et al. 2019.

## Third-party assets
- 3D astronaut: “astronaut” by Antropik — https://sketchfab.com/3d-models/astronaut-482bf87662fd4b378bcb3a2931d59ca3 — licensed CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). Modified by the LIASTRA team: textures recompressed, NASA insignia and mission patches removed (`models/astronaut.glb`).
- LIA robot: “RobotExpressive” by Tomás Laulhé (Quaternius), face morphs by Don McCurdy — CC0 1.0 (`models/robot.glb`).
- Crew members: Quaternius “Ultimate Modular Men” and “Ultimate Modular Women” packs — CC0 1.0; unused animations and a prop pistol removed, clothes recoloured in code (`models/crew-b.glb`, `crew-w1.glb`, `crew-w2.glb`).
- Three.js r128 and its GLTFLoader / SkeletonUtils / post-processing examples — MIT license (`vendor/`).

> Independent educational project. **Not an official NASA product** and not endorsed by NASA. No NASA logo is used.

## Controls
| Action | Keyboard | Touch |
|---|---|---|
| Look | Mouse (or hold the button and drag if the browser blocks pointer lock) | Drag on the right side |
| Move | W A S D (hold R to run) | Drag on the left side |
| Switch camera (1st / 3rd person) | Shift | Camera button (top right) |
| Interact / hold | E | Big button |
| Tablet (plan, map, greenhouse, glossary) | Tab | Tablet button |
| Pause | Esc | Menu button |

## Files
```
index.html     English version (submission build)
pt.html        Portuguese version of the same game (opened automatically on devices set to Portuguese; PT/EN link in the menu)
vendor/        Three.js r128, GLTFLoader, SkeletonUtils and post-processing modules (local, no CDN)
models/        astronaut.glb, robot.glb, crew-*.glb (rigged and animated; credits below)
.nojekyll      tells GitHub Pages to serve the files as they are
```

## Run locally
```
python3 -m http.server 8080
# open http://localhost:8080   (English)
# open http://localhost:8080/pt.html   (Portuguese)
```

## Deploy
**GitHub Pages:** push to `main`, then *Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)`*. The site is live in about a minute.
Netlify / Vercel: import the repo, no build command, publish directory `.`.

## Optional: NASA API key
The game uses `DEMO_KEY` (few requests per hour). Players can paste a free personal key from https://api.nasa.gov in the NASA data section; it is stored only in their browser.

## Progress storage
Patches, scores, XP, daily streak and settings are kept in the player's browser (`localStorage`, keys starting with `liastra.`). Nothing is sent to any server.
