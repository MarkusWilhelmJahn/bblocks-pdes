
# Volterra Predator-Prey with Carrying Capacity (Schema)

`mwj.pdes.o2.volterra` *v0.1*

Extended Volterra with logistic prey: dX/dt=r·X(1-X/K)-a·X·Y, dY/dt=-c·Y+d·a·X·Y. Volterra.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Volterra with Carrying Capacity

**Equation(s):**
```
dX/dt = r·X·(1-X/K) - a·X·Y\ndY/dt = -c·Y + d·a·X·Y
```

**Java class:** `model.lokal.o2.Volterra`
**Tags:** o2, predator-prey, logistic-prey

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "r": 0.5, "K": 50.0, "a": 0.02, "c": 0.3, "d": 0.5, "X0": 10.0, "Y0": 5.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: VolterraParameters
description: "Volterra predator-prey with logistic prey:\n  dX/dt = r\xB7X\xB7(1-X/K)
  - a\xB7X\xB7Y\n  dY/dt = -c\xB7Y + d\xB7a\xB7X\xB7Y\n"
type: object
required:
- r
- K
- a
- c
- d
- X0
- Y0
properties:
  r:
    type: number
    minimum: 0
    description: Prey intrinsic growth rate
  K:
    type: number
    minimum: 0
    description: Prey carrying capacity
  a:
    type: number
    minimum: 0
    description: Attack rate
  c:
    type: number
    minimum: 0
    description: Predator mortality rate
  d:
    type: number
    minimum: 0
    description: Conversion efficiency
  X0:
    type: number
    minimum: 0
  Y0:
    type: number
    minimum: 0
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/volterra/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/volterra/schema.yaml)


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
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/volterra/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/o2/volterra`

