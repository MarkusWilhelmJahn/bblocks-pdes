# Lorenz Chaotic System

**Equation(s):**
```
dx/dt = sigma·(y-x)\ndy/dt = x·(rho-z) - y\ndz/dt = x·y - beta·z
```

**Java class:** `model.lokal.o2.Lorenz`
**Tags:** o2, chaos, Lorenz-attractor

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
