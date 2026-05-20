# Simulation Result STAC Item

Generic **STAC 1.0 Feature** for any model run in FiniteDifferenceMethod4PDES.
Uses the `mwj-pdes` extension namespace (prefix → `https://mwj.example.org/pdes/stac/`).

## Key extension properties

| Property | Description |
|---|---|
| `mwj-pdes:model` | Human-readable model name |
| `mwj-pdes:modelClass` | Java class (e.g. `model.lokal.o2.Lorenz`) |
| `mwj-pdes:solver` | `jEuler` / `jRungeKutta` / `jButcher` |
| `mwj-pdes:dimensions` | 0 (ODE) / 1 / 2 / 3 (PDE) |
| `mwj-pdes:scenario` | Qualitative run label |
| `mwj-pdes:provenance` | → PROV `SimulationRun` (`prov:wasDerivedFrom`) |
| `mwj-pdes:observation` | → SOSA `ObservationCollection` (`prov:used`) |

## Context note

`mwj-pdes:provenance` maps to `prov:wasDerivedFrom` and `mwj-pdes:observation`
maps to `prov:used` via the context. The prefix `mwj-pdes` expands all other
extension properties automatically — no individual bindings needed.
