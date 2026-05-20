# Logistic Growth

**Equation(s):**
```
dX/dt = r·X·(1 - X/K)
```

**Java class:** `model.lokal.standard.Logistisch`
**Tags:** scalar, standard, carrying-capacity

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
