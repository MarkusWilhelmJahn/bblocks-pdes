# Stock-Independent Harvesting

**Equation(s):**
```
dX/dt = r·X·(1-X/K) - H
```

**Java class:** `model.lokal.o2.Bestandsunabhaengige_Ernte`
**Tags:** o2, harvesting, constant-quota

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
