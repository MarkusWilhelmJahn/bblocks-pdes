
# Generic Plankton Model (Schema)

`mwj.pdes.o2.plankton` *v0.1*

Simplified two-component phytoplankton-zooplankton model. Plankton.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Generic Plankton Model

**Equation(s):**
```
dP/dt = r·P·(1-P/K) - g·P·Z/(H+P)\ndZ/dt = e·g·P·Z/(H+P) - m·Z
```

**Java class:** `model.lokal.o2.Plankton`
**Tags:** o2, plankton, Holling-II

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "r": 0.5, "K": 10.0, "g": 0.4, "H": 1.0, "e": 0.6, "m": 0.2, "P0": 1.0, "Z0": 0.5 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: PlanktonParameters
description: "Simplified two-component phytoplankton(P)/zooplankton(Z) model:\n  dP/dt
  = r\xB7P\xB7(1-P/K) - g\xB7P\xB7Z/(H+P)\n  dZ/dt = e\xB7g\xB7P\xB7Z/(H+P) - m\xB7Z\n"
type: object
required:
- r
- K
- g
- H
- e
- m
- P0
- Z0
properties:
  r:
    type: number
    minimum: 0
    description: Phytoplankton growth rate [d^-1]
  K:
    type: number
    minimum: 0
    description: Phytoplankton carrying capacity
  g:
    type: number
    minimum: 0
    description: Max grazing rate (Holling II)
  H:
    type: number
    minimum: 0
    description: Half-saturation constant
  e:
    type: number
    minimum: 0
    maximum: 1
    description: Assimilation efficiency
  m:
    type: number
    minimum: 0
    description: Zooplankton mortality rate
  P0:
    type: number
    minimum: 0
    description: Initial phytoplankton
  Z0:
    type: number
    minimum: 0
    description: Initial zooplankton
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/o2/plankton/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/o2/plankton/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "plk": "https://mwj.example.org/pdes/model/",
    "prov": "http://www.w3.org/ns/prov#",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/o2/plankton/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/o2/plankton`

