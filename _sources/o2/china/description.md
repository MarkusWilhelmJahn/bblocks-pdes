# China Competition Model

**Equation(s):**
```
dX/dt = r1·X·(1-X/K1) - alpha12·X·Y\ndY/dt = r2·Y·(1-Y/K2) - alpha21·X·Y
```

**Java class:** `model.lokal.o2.China`
**Tags:** o2, competition, coexistence

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
