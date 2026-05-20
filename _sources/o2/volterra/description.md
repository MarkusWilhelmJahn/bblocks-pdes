# Volterra with Carrying Capacity

**Equation(s):**
```
dX/dt = r·X·(1-X/K) - a·X·Y\ndY/dt = -c·Y + d·a·X·Y
```

**Java class:** `model.lokal.o2.Volterra`
**Tags:** o2, predator-prey, logistic-prey

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
