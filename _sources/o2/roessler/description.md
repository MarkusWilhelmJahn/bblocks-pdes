# Rössler Chaotic System

**Equation(s):**
```
dx/dt = -(y+z)\ndy/dt = x + a·y\ndz/dt = b + z·(x-c)
```

**Java class:** `model.lokal.o2.Roessler`
**Tags:** o2, chaos, Roessler-attractor

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
