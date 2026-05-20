# Larch Budmoth (Tannentriebwickler)

**Equation(s):**
```
dN/dt = r·N/(1+alpha·N) - beta·N·Q\ndQ/dt = gamma·(Q_max-Q) - delta·N·Q
```

**Java class:** `model.lokal.o2.Tannentriebwickler`
**Tags:** o2, insect-outbreak, 9-year-cycle, Alps

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).
