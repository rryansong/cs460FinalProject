# cs460FinalProject

An interactive web demo inspired by 'Wonder Museam Light Floor' — a playful, techy space with animated sky, spark effects, two controllable block characters, and wandering cats that spawn hearts on contact.

## Overview
- **Scene**: Procedural cloud sky, a large floor, lights, and simple block characters.
- **Players**: Two characters with walking animation.
- **NPCs**: Two cats wander inside bounds; collisions spawn floating hearts.
- **Effects**: Shader-based sparks on steps with controllable color/intensity/size.
- **Camera**: Orbit/pan/zoom with a quick reset to the initial framing.
- **Music**: Optional background music with a keyboard toggle.

## Controls
- 'W A S D': Move the blue character.
- '↑ ↓ ← →': Move the red character.
- 'Mouse': Orbit, pan, and zoom the camera.
- 'R': Reset camera to the initial front-facing view.
- 'M': Toggle background music on/off.

## UI
- Top‑left panel: Spark color, intensity, and human spark size.
- Top‑right hint: Shows key mappings and the music/camera toggles.

## Music Setup
- The page uses an HTML '<audio>' element for background music.
- To use a local track, put 'shake-it-up-397500.mp3' next to 'index.html' and it will be loaded.
- Modern browsers may block autoplay; press 'M' once to start playback if needed.

## Tech Stack
- **Language**: HTML + JavaScript (ES Modules). No build step.
- **Rendering**: Three.js core ('Scene', 'PerspectiveCamera', 'WebGLRenderer').
- **Camera**: 'OrbitControls' for orbit, pan, and zoom; 'R' resets framing.
- **Geometry**: 'BoxGeometry', 'PlaneGeometry', 'ConeGeometry', 'CylinderGeometry' to build people and cats.
- **Materials**:
	- 'MeshStandardMaterial' for most meshes (lit by Hemisphere + Directional lights).
	- 'ShaderMaterial' for the sky dome and spark particles.
- **Shaders (GLSL)**:
	- Sky dome with procedural clouds and time animation.
	- Custom particle system (vertex + fragment) with per‑particle size/fade and additive blending.
- **Animation**: 'requestAnimationFrame' loop + 'THREE.Clock'; walking gait, step cadence, and cat wandering.
- **Particles**: 'BufferGeometry' with custom attributes ('aLife', 'aSize'), CPU‑spawned bursts, GPU‑faded.
- **Audio**: HTML5 '<audio>' for background music; 'M' toggles play/pause.
- **UI/DOM**: Simple inputs for spark color/intensity/size; top‑right hint overlay.
- **Input**: Keyboard events for WASD and Arrow keys; collision detection with cats.
- **Hosting**: Works as a static page; run with a local server (e.g., 'python -m http.server').
- **Targets**: Modern browsers supporting ES Modules and WebGL.

## Notes
- Characters and cats are kept within floor bounds.
- Cat collisions spawn 5 hearts that float up and fade while cats keep running.
- Spark size slider increases spread while reducing particle count to balance performance.

## Inspiration
- This project is inspired by 'Wonder Museam Light Floor'.

