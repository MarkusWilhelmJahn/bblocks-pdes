
# Lotka-Volterra Predator-Prey (Schema)

`mwj.pdes.o2.lotka-volterra` *v0.1*

Classic Lotka-Volterra: dX/dt=a·X-b·X·Y, dY/dt=-c·Y+d·X·Y. Implemented in Lotka.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Lotka-Volterra Predator-Prey

**Equation(s):**
```
dX/dt = a·X - b·X·Y\ndY/dt = -c·Y + d·X·Y
```

**Java class:** `model.lokal.o2.Lotka`
**Tags:** o2, predator-prey, Holling-I

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "a": 0.5, "b": 0.02, "c": 0.3, "d": 0.01, "X0": 10.0, "Y0": 5.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: LotkaVolterraParameters
description: "Classic Lotka-Volterra predator-prey:\n  dX/dt = a\xB7X - b\xB7X\xB7Y
  \  (prey)\n  dY/dt = -c\xB7Y + d\xB7X\xB7Y  (predator)\n"
type: object
required:
- a
- b
- c
- d
- X0
- Y0
properties:
  a:
    type: number
    minimum: 0
    description: Prey growth rate [d^-1]
  b:
    type: number
    minimum: 0
    description: Predation rate coefficient
  c:
    type: number
    minimum: 0
    description: Predator mortality rate [d^-1]
  d:
    type: number
    minimum: 0
    description: Predator growth efficiency
  X0:
    type: number
    minimum: 0
    description: Initial prey density
  Y0:
    type: number
    minimum: 0
    description: Initial predator density
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/lotka-volterra/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/lotka-volterra/schema.yaml)


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
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/lotka-volterra/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/o2/lotka-volterra`

