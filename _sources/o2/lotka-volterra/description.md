# Lotka-Volterra Predator-Prey

**Equation(s):**
```
dX/dt = a·X - b·X·Y\ndY/dt = -c·Y + d·X·Y
```

**Java class:** `model.lokal.o2.Lotka`
**Tags:** o2, predator-prey, Holling-I

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
