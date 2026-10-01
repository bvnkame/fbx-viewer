# FBX Studio

Free, browser-based FBX viewer and animation tool. Everything runs locally in your browser: files are never uploaded.

**Live demo:** https://YOUR-USERNAME.github.io/fbx-viewer/

## Features

- Open `.fbx` files (drag & drop or file picker), orbit / zoom / pan, frame model
- Wireframe, mesh, textures and grid toggles; skeleton (bones) overlay
- Outliner: node hierarchy with click-to-highlight, texture list with thumbnails
- Animation panel: play, pause, scrub, loop, speed; clip list with inline rename
- Blend: mix two clips by weight or crossfade A → B, preview, then bake as a new clip (saved in FBX / GLB)
- Visual AnimationTree editor (Godot style): state machine graph with draggable states and transitions (xfade, immediate / at end), BlendSpace1D and BlendSpace2D editors with draggable points and blend position, live preview on the model, bake any blend position to a clip
- Merge animations: add animation-only FBX files (e.g. Mixamo "Without Skin") to a model and play them
- Export: FBX (original file + renamed and added clips), Godot 4 (GLB + .tscn with AnimationTree), GLB, GLB (animation only), GLTF, OBJ, STL, PLY
- Recent projects (stored in your browser's IndexedDB), including renamed and added clips

## Usage tips

- External textures: drop the image files (png / jpg / webp) together with the FBX.
- Added animations must use the same rig (bone names) as the model. Mixamo to Mixamo works.
- OBJ / STL / PLY export the mesh at the current animation pose.
- Godot export: unzip both files into the same folder of a Godot 4.2+ project and open the .tscn. The scene's AnimationTree mirrors the visual editor: states, BlendSpace1D / BlendSpace2D points and blend positions, transitions and node positions. Enable Loop in the GLB import dialog for looping clips.
- FBX export rewrites the original binary FBX: mesh, skin and materials stay untouched, clips are renamed and added clips are appended as new animation stacks. ASCII FBX cannot be saved.

## Run locally

Open `index.html` in a browser (needs internet for the CDN scripts), or serve the folder with any static server.

## Deploy on GitHub Pages

Repository Settings, Pages, Source: *Deploy from a branch*, branch `main`, folder `/ (root)`.

## Credits and licenses

- [three.js](https://threejs.org) r147 (MIT) and [fflate](https://github.com/101arrowz/fflate) (MIT), loaded from jsDelivr.
- Built-in samples are **not** stored in this repository. They are fetched on click from the [three.js examples](https://github.com/mrdoob/three.js/tree/r170/examples/models/fbx). The Mixamo-sourced samples belong to Mixamo / Adobe and the Stanford Bunny to the Stanford Computer Graphics Laboratory: use them for testing only and check their terms before reusing.
- This project's code: MIT, see `LICENSE`.
