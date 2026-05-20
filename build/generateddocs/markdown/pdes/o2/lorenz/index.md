
# Lorenz System (Schema)

`mwj.pdes.o2.lorenz` *v0.1*

Lorenz (1963) chaotic attractor: dx/dt=sigma(y-x), dy/dt=x(rho-z)-y, dz/dt=xy-beta·z. Lorenz.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Lorenz Chaotic System

**Equation(s):**
```
dx/dt = sigma·(y-x)\ndy/dt = x·(rho-z) - y\ndz/dt = x·y - beta·z
```

**Java class:** `model.lokal.o2.Lorenz`
**Tags:** o2, chaos, Lorenz-attractor

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "sigma": 10.0, "rho": 28.0, "beta": 2.6667, "x0": 0.1, "y0": 0.0, "z0": 0.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: LorenzParameters
description: "Lorenz (1963) chaotic attractor:\n  dx/dt = sigma\xB7(y - x)\n  dy/dt
  = x\xB7(rho - z) - y\n  dz/dt = x\xB7y - beta\xB7z\n"
type: object
required:
- sigma
- rho
- beta
- x0
- y0
- z0
properties:
  sigma:
    type: number
    minimum: 0
    default: 10.0
    description: Prandtl number
  rho:
    type: number
    minimum: 0
    default: 28.0
    description: "Rayleigh number \u2014 bifurcation parameter"
  beta:
    type: number
    minimum: 0
    default: 2.666667
    description: Geometric parameter (8/3)
  x0:
    type: number
    default: 0.1
    description: Initial x (convection amplitude)
  y0:
    type: number
    default: 0.0
    description: Initial y (horizontal temperature)
  z0:
    type: number
    default: 0.0
    description: Initial z (vertical temperature)
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/lorenz/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/lorenz/schema.yaml)


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
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/lorenz/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/o2/lorenz`

