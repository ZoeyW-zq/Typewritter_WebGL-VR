# Typewriter — WebGL & VR Interactive Prototype

A Unity interactive prototype built for DDES9912. It places a working typewriter in a 3D environment: pressing its keys prints characters onto paper, while the carriage and paper move as part of the typing interaction. Animated typist characters work at other typewriters, and a walking character collects completed pages.

The project contains a desktop WebGL scene and a separate VR scene. The checked-in WebGL build is in [`Builds/`](Builds/).

## Experience

- Interact with the typewriter's keys to print characters on the inserted sheet. Shift and shift-lock states provide alternate characters.
- Use the typewriter's paper controls to advance or replace the sheet.
- Watch the typist characters type, remove finished pages, load new paper, and hand pages to the walking collector.
- Place a finished page at the collection point to call the collector. The scene tracks the number of collected pages.

## Run the project

### In Unity

1. Open the repository folder with **Unity 6000.3.8f1** (the version recorded in [`ProjectVersion.txt`](ProjectSettings/ProjectVersion.txt)).
2. Open [`Typewritter_Web_done.unity`](Assets/__My%20Project/Scene/Typewritter_Web_done.unity) and press **Play** for the desktop scene. This is the scene enabled in Build Settings.
3. For the VR version, open [`Typewritter_VR.unity`](Assets/__My%20Project/Scene/Typewritter_VR.unity) instead. It uses Unity XR packages and requires a compatible, configured XR setup; it is not part of the current WebGL build.

### Play the checked-in WebGL build

Serve [`Builds/`](Builds/) from a local HTTP server, then open the server URL in a desktop browser. For example, from the repository root:

```sh
python -m http.server 8000 --directory Builds
```

Open `http://localhost:8000/`. The WebGL files should be served together; opening `Builds/index.html` directly from the filesystem may fail to load the Unity data files.

## Project layout

| Path | Contents |
| --- | --- |
| [`Assets/__My Project/Scene/`](Assets/__My%20Project/Scene/) | Main WebGL and VR scenes, plus a controller hand test scene |
| [`Assets/__My Project/Scripts/`](Assets/__My%20Project/Scripts/) | Typewriter, paper, NPC, and VR hand interaction scripts |
| [`Assets/__My Project/Prefabs/`](Assets/__My%20Project/Prefabs/) | Typewriter, key, paper, and XR prefabs |
| [`Builds/`](Builds/) | Exported WebGL player and build files |
| [`Assets/EZPZ Interaction Toolkit/`](Assets/EZPZ%20Interaction%20Toolkit/) | Matt Cabanag's interaction toolkit used by this project |

## Tools and credits

Built with Unity 6, the Universal Render Pipeline, the Input System, XR Interaction Toolkit, XR Hands, OpenXR, Animation Rigging, and TextMesh Pro. Package versions are recorded in [`Packages/manifest.json`](Packages/manifest.json).

This project uses **EZPZ Interaction Toolkit by Matt Cabanag**, provided as part of the course. In particular, project scripts use its interaction triggers and character navigation components. The toolkit is licensed under the **MIT License**; its copyright notice, license text, and third-party asset references are in [`Assets/README_EZPZ.txt`](Assets/README_EZPZ.txt). See the [toolkit guide](https://youtu.be/GZrhy2qOsnE) and [Matt Cabanag's profile](https://www.linkedin.com/in/mattavc/) for more information. The repository also includes [Proyecto26 RestClient](https://github.com/proyecto26/RestClient).

The toolkit's MIT license applies to the toolkit, not automatically to every original or third-party asset in this repository.
