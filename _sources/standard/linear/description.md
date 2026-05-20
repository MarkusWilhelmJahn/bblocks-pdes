# Linear ODE

**Equation(s):**
```
dX/dt = a·X + b
```

**Java class:** `model.lokal.standard.Linear`
**Tags:** scalar, standard, linear

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
