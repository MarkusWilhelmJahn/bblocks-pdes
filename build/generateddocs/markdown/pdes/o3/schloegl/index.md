
# Schlögl Bistable Chemical Reaction (Schema)

`mwj.pdes.o3.schloegl` *v0.1*

Schlögl (1972) chemical bistability: dX/dt = k1·A·X²-k2·X³+k3·B-k4·X. Schloegl.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Schlögl Bistable Chemical Reaction

**Equation(s):**
```
dX/dt = k1·A·X² - k2·X³ + k3·B - k4·X\n(first-order phase transition at critical A/B values)
```

**Java class:** `model.lokal.o3.Schloegl`
**Tags:** o3, bistability, chemical-kinetics, Schloegl-model

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "k1": 3e-7, "k2": 1e-4, "k3": 1e-3, "k4": 3.5, "A": 1e5, "B": 2e5, "X0": 250.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: SchloeglParameters
description: "Schl\xF6gl (1972) bistable chemical reaction:\n  A + 2X <-> 3X  (autocatalytic)\n
  \ B + X  <-> C   (drain)\n  dX/dt = k1\xB7A\xB7X\xB2 - k2\xB7X\xB3 + k3\xB7B - k4\xB7X\nControl
  parameter: A or B drives first-order phase transition.\n"
type: object
required:
- k1
- k2
- k3
- k4
- A
- B
- X0
properties:
  k1:
    type: number
    minimum: 0
    description: Forward rate constant (autocatalysis)
  k2:
    type: number
    minimum: 0
    description: Reverse rate constant (autocatalysis)
  k3:
    type: number
    minimum: 0
    description: Forward rate constant (drain)
  k4:
    type: number
    minimum: 0
    description: Reverse rate constant (drain)
  A:
    type: number
    minimum: 0
    description: Concentration of species A (control)
  B:
    type: number
    minimum: 0
    description: Concentration of species B (control)
  X0:
    type: number
    minimum: 0
    description: Initial concentration of X
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o3/schloegl/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o3/schloegl/schema.yaml)


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
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o3/schloegl/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/o3/schloegl`

