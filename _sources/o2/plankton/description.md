# Generic Plankton Model

**Equation(s):**
```
dP/dt = r·P·(1-P/K) - g·P·Z/(H+P)\ndZ/dt = e·g·P·Z/(H+P) - m·Z
```

**Java class:** `model.lokal.o2.Plankton`
**Tags:** o2, plankton, Holling-II

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
