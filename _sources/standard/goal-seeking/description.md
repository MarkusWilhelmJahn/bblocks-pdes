# Goal-Seeking Model

**Equation(s):**
```
dX/dt = r·(Z - X)
```

**Java class:** `model.lokal.standard.Zielsuchend`
**Tags:** scalar, standard, control

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
