# Scheffer Phytoplankton-Zooplankton (RDA)

**Equation(s):**
```
dX1/dt = alpha·N/(HN+N)·X1 - c·X1² - gamma·X1/(H1+X1)·X2 - v1·∇X1 + D1·∇²X1\ndX2/dt = e·gamma·X1/(H1+X1)·X2 - delta·X2 - F·X2²/(H2²+X2²) - v2·∇X2 + D2·∇²X2
```

**Java class:** `model.lokal.o2.Scheffer`
**Tags:** o2, plankton, RDA, Holling-II, Holling-III, Turing, DIFICI

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
