# CLAUDE.md

This file provides guidance to Claude Code when working with code in this repository.

## Project Overview

**Panrama in VR** - A web-based VR180 hemispherical photo viewer for Philippe Jaulmes' Panrama collection (1966-2010).

- **Live site**: https://a1rb4ck.github.io/panrama/
- **Tech stack**: Three.js, WebXR, vanilla JavaScript
- **Targets**: VR headsets (Quest, Vision Pro, Pico) + desktop/mobile browsers

## Architecture

```
index.html                    # Entry point, media playlist
lifecast_res/
  LifecastVideoPlayer11.js    # Main player (init, render loop, controls)
  Vr180Mesh.js               # VR180 stereo hemisphere mesh
  SBSMesh.js                 # Side-by-side stereo format
  Mesh180.js                 # Mono 180° format
  GestureControlModule.js    # Hand tracking gestures
  HelpGetVR11.js             # VR button and WebXR setup
  OrbitControls.js           # Desktop camera controls
dist/
  lifecast.min.js            # Webpack bundle (production)
media/                       # Panoramic images (~22 images)
```

## Key Concepts

- **Format modes**: `vr180` (stereo), `sbs` (side-by-side), `180` (mono) - set in init()
- **Playlist**: Array of image paths in index.html, navigated with prev/next
- **Controls**: Desktop (mouse/keyboard/scroll), VR (controllers A/B buttons, triggers, hand tracking)
- **Rendering**: Two-pass (world_group for content, interface_group for UI)

## Development

```bash
npm install && npm run build   # Build dist/lifecast.min.js
python3 -m http.server 8080    # Local testing (or use local_server_https.py for VR)
```

## Development Philosophy

**Context**: Solo developer, personal project. Ship over perfect architecture.

- Assume POC unless told otherwise
- Keep it simple - no unnecessary abstractions
- Hardcode reasonable defaults
- Don't over-engineer for imaginary future requirements

## When Editing

- The player is adapted from LifeCastVR - preserve the MIT license headers
- Adding images: add to `media/` folder and update playlist in `index.html`
- Test on desktop first, then VR headset if available
- WebXR requires HTTPS for VR testing on headsets (use local_server_https.py)
