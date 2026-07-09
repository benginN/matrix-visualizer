# Matrix Visualizer

Interactive visualizer for 2×2 and 3×3 linear transformations — a single self-contained HTML file, no dependencies, no build step.

**[Live demo →](https://benginn.github.io/matrix-visualizer/)**

## Features

- **Animated transformations** — smooth interpolation `M(t) = (1−t)·I + t·M` from identity to the target matrix. This interpolation keeps every eigendirection of `M` invariant for all `t`, so you can watch the grid slide along the eigenlines.
- **2D mode** — draggable basis vectors (î, ĵ), transformed grid, unit square with live determinant, eigenlines with eigenvalue labels, unit circle → ellipse (singular values), axis ticks.
- **3D mode** — orbit camera, transformed lattice, unit cube → parallelepiped, eigenlines *and* eigenplanes (for repeated eigenvalues), unit sphere → ellipsoid.
- **Full analysis panel** — determinant, trace, rank, eigenvalues (including complex pairs), eigenvectors, singular values, characteristic polynomial, and automatic classification (rotation, shear, reflection, projection, symmetric, singular, …).
- **Decompositions** — diagonalization `M = P·D·P⁻¹` when possible, otherwise the **Jordan normal form** `M = P·J·P⁻¹` with generalized eigenvectors (all 3×3 block structures supported), the **real canonical form** `M = P·C·P⁻¹` for complex eigenvalues, and the inverse `M⁻¹`.
- **Shareable URLs** — the matrix and mode are encoded in the URL hash (`#3d:…`), so any state can be shared as a link.
- 24 presets across both modes: rotations, shears, reflections, projections, spirals, singular and symmetric matrices.

## Usage

Open `index.html` in a browser. That's it.

| Interaction | Effect |
| --- | --- |
| Drag î / ĵ tips (2D) | Edit the matrix directly (⇧ snaps to 0.5) |
| Drag (3D) | Orbit the camera |
| Scroll | Zoom |
| Space | Play / pause the animation |

All the math (eigendecomposition via analytic quadratic/cubic solvers, Jordan chains, complex eigenvectors, SVD values) is implemented from scratch in the single file.
