
# Logistic Growth (Schema)

`mwj.pdes.standard.logistic` *v0.1*

Single-species logistic growth dX/dt = r·X·(1-X/K). Implemented in Logistisch.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Logistic Growth

**Equation(s):**
```
dX/dt = r·X·(1 - X/K)
```

**Java class:** `model.lokal.standard.Logistisch`
**Tags:** scalar, standard, carrying-capacity

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "r": 0.5, "K": 10.0, "X0": 1.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: LogisticParameters
description: "dX/dt = r\xB7X\xB7(1 - X/K)"
type: object
required:
- r
- K
- X0
properties:
  r:
    type: number
    description: Intrinsic growth rate [d^-1]
  K:
    type: number
    minimum: 0
    description: Carrying capacity
  X0:
    type: number
    minimum: 0
    description: Initial population
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/standard/logistic/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/standard/logistic/schema.yaml)


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
[context.jsonld](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/standard/logistic/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/standard/logistic`

