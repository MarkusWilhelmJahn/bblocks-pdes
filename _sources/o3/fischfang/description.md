# Fish Harvesting (Fischfang)

**Equation(s):**
```
dN/dt = r_N - k·N·F\ndF/dt = e·k·N·F - m·F - q·E·F\ndE/dt = p·(q·pF·F - c)·E
```

**Java class:** `model.lokal.o3.Fischfang`
**Tags:** o3, fisheries, bioeconomics, effort-dynamics

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
