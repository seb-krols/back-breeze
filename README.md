# BackBreeze

> A parametric mesh generator for 3D-printable backpack ventilation inserts — built because Singapore is humid and existing solutions don't work.

<video src="https://github.com/user-attachments/assets/73a85a21-50fc-47c4-8c07-aee0fcbc4a83" autoplay loop muted playsinline width="100%"></video>

---

## The Problem

Carrying a backpack in Singapore means a sweaty back — guaranteed. The gap between your back and the bag is sealed shut, no airflow, no escape. Existing solutions (padded backs, mesh panels built into bags) are either ineffective or require buying a whole new bag.

The real fix is structural: create a physical air gap with a rigid-but-flexible insert that sits between your back and the bag, open at the edges for air intake and strong enough in the center to bear the load.

---

## What BackBreeze Does

BackBreeze generates parametric TPU mesh inserts — 3D-printable, ergonomically shaped, and structurally engineered for ventilation. The core innovation is **gradient density**: the mesh is open and airy at the edges where air flows in, and progressively denser toward the spine where structural support matters.

The insert follows an ergonomic S-curve back profile, adapting to lumbar and thoracic curvature so it actually sits flush against your back rather than bridging awkwardly.

<img width="2523" height="1599" alt="BackBreeze mesh configurator" src="https://github.com/user-attachments/assets/ef5960db-21d1-497c-889a-56ccc9d85ec7" />

---

## Architecture

BackBreeze is built in two layers:

**Python Generation Engine**
The core mesh generator handles all the hard geometry: pattern generation (honeycomb, diamond, Voronoi), gradient density mapping, S-curve profile projection, TPU printability validation (minimum 1.2mm feature size enforcement), and STL export. Runs as a standalone Python tool or called programmatically via API.

**React Web Configurator**
A browser-based interface wrapping the generation engine. Customers configure their insert using simplified controls — airflow level (1–5), weight support category, backpack size preset — which map to the underlying parametric parameters. The 3D mesh preview updates in-browser with full rotation and zoom. Configurations are submitted as orders capturing all generation parameters.

---

## Tech Stack

| Layer | Tools |
|---|---|
| Mesh Generation | Python, Pydantic, NumPy |
| API | FastAPI |
| Web Frontend | React, Vite, Tailwind CSS, Zustand |
| 3D Viewer | React Three Fiber (R3F) |
| Export | STL (watertight, manifold, print-ready) |

---

## Key Features

- **3 mesh patterns** — honeycomb, diamond, Voronoi — each with different structural and airflow characteristics
- **Gradient density control** — open edges for air intake, dense center for load bearing, adjustable gradient curve
- **Ergonomic S-curve profile** — configurable lumbar depth and thoracic curve, not a flat slab
- **Airflow analysis** — drag coefficient, open area ratio, contact surface area, sweat resistance score
- **TPU printability enforcement** — minimum 1.2mm feature size, watertight manifold geometry, print validation warnings
- **Dual workflow** — quick preview mode (<2s) for iteration, high-resolution STL export for production
- **Browser 3D configurator** — live mesh preview, simplified controls, order submission

---

## Status

| Phase | Description | Status |
|---|---|---|
| 1 | Core generation pipeline | ✅ Complete |
| 2 | Advanced shaping & airflow analysis | ✅ Complete |
| 3 | Python workflow & STL export | ✅ Complete |
| 4 | Web viewer & configurator | ✅ Complete |

v1 complete. Actively refining mesh quality, print validation, and configurator UX.

---

## This is a Showcase

This is a public showcase of a private project. Source code is kept private — the IP here is in the geometry engine and gradient density approach, and I intend to commercialize it.

Interested in collaborating, printing a prototype, or just want to talk through the approach? Reach out.

---

## Contact

**Sebastian Krols**
[github.com/seb-krols](https://github.com/seb-krols) · [LinkedIn](https://linkedin.com/in/sebastiankrols)

---

*© 2026 Sebastian Krols. All rights reserved.*
