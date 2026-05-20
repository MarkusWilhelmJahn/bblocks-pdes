# Exponential Growth

**Equation(s):**
```
dX/dt = r·X
```

**Java class:** `model.lokal.standard.Exponentiell`
**Tags:** scalar, standard, growth

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
