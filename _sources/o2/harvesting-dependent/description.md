# Stock-Dependent Harvesting

**Equation(s):**
```
dX/dt = r·X·(1-X/K) - q·E·X\ndE/dt = p·(q·pX·X - c)·E
```

**Java class:** `model.lokal.o2.Bestandsabhaengige_Ernte`
**Tags:** o2, harvesting, bioeconomics, MSY

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
