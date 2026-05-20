# Lead Kinetics (Blei)

**Equation(s):**
```
dX/dt = k_in - k_out·X   [X = blood lead concentration µg/dl]
```

**Java class:** `model.lokal.o1.Blei`
**Tags:** o1, toxicokinetics, lead

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
