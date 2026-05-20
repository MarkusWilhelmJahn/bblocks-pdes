# Tumor-Immune Interaction

**Equation(s):**
```
dT/dt = r·T·(1-T/K) - k·T·I\ndI/dt = sigma - mu·I + alpha·T·I/(1+beta·T)
```

**Java class:** `model.lokal.o2.Tumor`
**Tags:** o2, oncology, immune-response

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
