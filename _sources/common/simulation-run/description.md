# Simulation Run (PROV)

Generic **`prov:Activity`** for any model execution in FiniteDifferenceMethod4PDES.

## Architecture

The software follows an MVC pattern:
- **Model** — local kinetic classes (`model/lokal/`) + spatial operators (`model/global/`)
- **Numerik** — solvers: `jEuler`, `jRungeKutta`, `jButcher` (`model/numerik/`)
- **View** — plotters: `JPlotter0D/1D/2D`, `VTKPlotter0D/3D` (`view/`)
- **GUI** — `MainPanel`, `MainPanelController`, `Simulator`

## PROV alignment

```
sosa:ObservationCollection ──prov:used──► SimulationRun (prov:Activity)
Parameter set (prov:Entity) ──prov:used──►       │ wasAssociatedWith
                               FiniteDifferenceMethod4PDES (prov:Agent)
                                          prov:wasGeneratedBy
                                    ┌────────────▼────────────┐
                                    │ timeseries-csv           │
                                    │ spatial-field-vtk        │
                                    │ plot-*.png               │
                                    └──────────────────────────┘
                                               │ dcat:landingPage
                                         STAC Item
```

## Concrete model blocks

Each concrete model block (e.g. `mwj.pdes.o2.scheffer`) extends this schema
by adding its specific `parameters` sub-schema.
