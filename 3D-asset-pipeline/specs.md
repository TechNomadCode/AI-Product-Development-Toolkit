# Master Technical Brief: Complete Hybrid AI Pipeline

## 1. Executive Summary & Architecture

This pipeline allows a developer with **zero manual 3D/Blender experience** to build a 3D hack-and-slash game. 

* **You (Human):** Handle all creative generation, visual previewing, texture painting, lighting map creation, and file downloads in the Rodin Web GUI Suite (0% credit burn risk).
* **Claude Code:** Handles automated inspection and data cleanup via Blender Lab MCP, local file management, and writing Game Engine code (C#/GDScript).
* **Mixamo / AccuRig:** Handle automated skeletal rigging and combat animations for free.

---

## 2. Division of Labor & Tool Responsibilities

### You (Human Director) — Environment: Rodin Web GUI & Mixamo
* **Core 3D Generation:** Text-to-3D, Image-to-3D, T-Pose selection, Smart Low-Poly exports.
* **AI Texture Generator:** Repaint untextured base meshes with AI PBR textures directly in the browser.
* **HDRI Generation:** Create 360-degree environment lighting maps for dark fantasy dungeon skyboxes.
* **Vector to 3D:** Convert 2D SVG vector icons/runes into 3D emblems, coins, or wall decor.
* **Image Enhancer & Remix:** Polish and clean up 2D concept art before generating 3D models.
* **Rodin Search & BANG Part Split:** Search pre-made assets and split modular armor, weapons, or character parts.
* **Rigging & Animations:** Drag-and-drop character FBXs into Mixamo or AccuRig (maybe Cascadeur) for free auto-rigging and combat animation downloads.

### Claude Code (Technical Director) — Environment: Terminal, Blender MCP & Game Engine
* **Viewport Inspection:** Use Blender MCP viewport screenshots to visually check asset scale, facing direction (`-Z`), and ground plane alignment `(0,0,0)`.
* **Diagnostic Audits:** Run non-destructive mesh health checks (polycounts, non-manifold edges).
* **Material & File Cleanup:** Rename materials (`M_Name`), set up PBR shader nodes, and export clean FBX files to engine directories.
* **Scene debugging:** Find out what the object with the highest poly-count is on file that is linked to any scene. 
* **Geometry Nodes Documentation:** Explain what the main geometry nodes setup is doing

These are just examples. Go to https://www.blender.org/lab/mcp-server/ for official, tested use cases.

---

## 3. Cost Structure & Safety Guarantee

Only two tools in the entire pipeline carry financial costs:

1. **Rodin 3D (Business Plan):** **Paid** (Credit consumption for 3D meshes, textures, HDRIs, and Vector-to-3D is 100% human-controlled in the Web GUI; zero chance of autonomous API credit burn).
2. **Claude Code:** **Paid** (Subscription or API usage).
3. **Blender & Official Blender Lab MCP Server:** **100% Free** (Open Source GPL).
4. **Mixamo & AccuRig:** **100% Free** (Adobe / Reallusion auto-rigging services).
5. **Game Engine (Godot / Unity / Unreal):** **100% Free** (Free Tiers or Open Source).

---

## 4. Hand-Off Pipeline Flow

```
[1. YOU: Full Rodin Web Suite]
  - Generate 3D Meshes (T-Pose, Smart Low-Poly)
  - Paint PBR Textures via AI Texture Generator
  - Generate Dungeon HDRIs & Convert Vector Runes to 3D
  - Download finished FBXs/HDRIs to /raw_imports/
        │
        ▼
[2. CLAUDE CODE: Blender Lab MCP Server]
  - Viewport screenshot check (scale, orientation, ground alignment)
  - Diagnostic polycount & manifold health audit
  - Material renaming & clean export to engine folders

        │
        ▼
[3. YOU: Mixamo / AccuRig Web]
  - Drag-and-drop character FBXs for free auto-rigging
  - Download combat animation clips
        │
        ▼
[4. CLAUDE CODE: Game Engine]
  - Apply Rodin HDRIs & Materials
  - Write C#/GDScript logic for weapon sockets, state machines, procedural dungeons
```

---

## 5. Non-Destructive Blender MCP Rules

When Claude Code processes your downloaded Rodin assets in Blender:

* **Allowed Actions:** Viewport screenshot vision checks, setting pivot origins to ground level `(0,0,0)`, live polycount readouts, non-manifold geometry diagnostics, material renaming (`M_Name`), and clean FBX/GLB exports.
* **Prohibited Actions:** No custom Python geometry math scripts (decimation, sculpting, manual retopology) to avoid ruining Rodin's visual mesh quality.

---

## 6. Final Summary Statement

With the complete Rodin Web Suite at your fingertips, you act as the **Creative Director**—generating models, textures, vector emblems, and dungeon HDRIs directly in your browser with zero financial risk. Once downloaded, **Claude Code takes over as the Technical Director**, automating Blender inspection and writing all the engine C#/GDScript code to turn your assets into a playable game.