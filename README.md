# Matrix Visualizer

Interactive visualizer for 2×2 and 3×3 linear transformations — a single self-contained HTML file, no dependencies, no build step.

**[Live demo →](https://benginn.github.io/matrix-visualizer/)**

## Features

- **Animated transformations** — two animation paths:
  - **blend**: `M(t) = (1−t)·I + t·M`, which keeps every eigendirection of `M` invariant for all `t`, so you can watch the grid slide along the eigenlines;
  - **rotate · scale · rotate**: the motion is decomposed into its SVD steps `M = U·Σ·Vᵀ` and played as rotation → axis scaling → rotation (in 3D via axis–angle interpolation of `U` and `Vᵀ`).
- **2D mode** — draggable basis vectors (î, ĵ), transformed grid, unit square with live determinant, eigenlines with eigenvalue labels, unit circle → ellipse (singular values), axis ticks.
- **3D mode** — orbit camera, transformed lattice, unit cube → parallelepiped, eigenlines *and* eigenplanes (for repeated eigenvalues), unit sphere → ellipsoid.
- **Full analysis panel** — determinant, trace, rank, eigenvalues (including complex pairs), eigenvectors, singular values, characteristic polynomial, and automatic classification (rotation, shear, reflection, projection, symmetric, singular, …).
- **Decompositions** — diagonalization `M = P·D·P⁻¹` when possible, otherwise the **Jordan normal form** `M = P·J·P⁻¹` with generalized eigenvectors (all 3×3 block structures supported), the **real canonical form** `M = P·C·P⁻¹` for complex eigenvalues, the full **SVD** `M = U·Σ·Vᵀ`, and the inverse `M⁻¹`.
- **Probe vector** (2D) — double-click anywhere to drop an input vector `v` and watch `M(t)·v` move with live coordinates; drag its tip to reposition, double-click it to remove.
- **Quick operations** — one-click `Mᵀ`, `M⁻¹`, `−M`, `M²`; ⇧-click any preset to compose it onto the current matrix.
- **Shareable URLs** — the matrix and mode are encoded in the URL hash (`#3d:…`), so any state can be shared as a link.
- 24 presets across both modes: rotations, shears, reflections, projections, spirals, singular and symmetric matrices.

## Usage

Open `index.html` in a browser. That's it.

| Interaction | Effect |
| --- | --- |
| Drag î / ĵ tips (2D) | Edit the matrix directly (⇧ snaps to 0.5) |
| Double-click (2D) | Place / remove a probe vector |
| ⇧-click a preset | Compose it onto the current matrix |
| Drag (3D) | Orbit the camera |
| Scroll | Zoom |
| Space | Play / pause the animation |

All the math (eigendecomposition via analytic quadratic/cubic solvers, Jordan chains, complex eigenvectors, SVD values) is implemented from scratch in the single file.
