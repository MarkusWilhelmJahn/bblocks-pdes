# Schlögl Bistable Chemical Reaction

**Equation(s):**
```
dX/dt = k1·A·X² - k2·X³ + k3·B - k4·X\n(first-order phase transition at critical A/B values)
```

**Java class:** `model.lokal.o3.Schloegl`
**Tags:** o3, bistability, chemical-kinetics, Schloegl-model

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
