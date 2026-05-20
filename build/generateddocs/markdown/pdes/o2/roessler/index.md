
# Rössler System (Schema)

`mwj.pdes.o2.roessler` *v0.1*

Rössler (1976) chaotic system: dx/dt=-(y+z), dy/dt=x+a·y, dz/dt=b+z(x-c). Roessler.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

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

## Examples

### Default parameter set
{ "a": 0.2, "b": 0.2, "c": 5.7, "x0": 0.1, "y0": 0.0, "z0": 0.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: RoesslerParameters
description: "R\xF6ssler (1976) chaotic system:\n  dx/dt = -(y + z)\n  dy/dt = x +
  a\xB7y\n  dz/dt = b + z\xB7(x - c)\n"
type: object
required:
- a
- b
- c
- x0
- y0
- z0
properties:
  a:
    type: number
    default: 0.2
    description: Coupling parameter
  b:
    type: number
    default: 0.2
    description: Constant forcing
  c:
    type: number
    default: 5.7
    description: Bifurcation parameter
  x0:
    type: number
    default: 0.1
  y0:
    type: number
    default: 0.0
  z0:
    type: number
    default: 0.0
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/roessler/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/roessler/schema.yaml)


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
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/roessler/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/o2/roessler`

