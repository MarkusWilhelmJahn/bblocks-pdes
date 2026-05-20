# Jansen Host-Parasitoid Model

**Equation(s):**
```
dN/dt = lambda·N·exp(-a·P) - N\ndP/dt = N·(1 - exp(-a·P)) - mu·P
```

**Java class:** `model.lokal.o2.Jansen`
**Tags:** o2, host-parasitoid, cycles

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
