
# China Population Model (Schema)

`mwj.pdes.o2.china` *v0.1*

Two-component demographic or resource-competition model. China.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# China Competition Model

**Equation(s):**
```
dX/dt = r1·X·(1-X/K1) - alpha12·X·Y\ndY/dt = r2·Y·(1-Y/K2) - alpha21·X·Y
```

**Java class:** `model.lokal.o2.China`
**Tags:** o2, competition, coexistence

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "r1": 0.5, "K1": 100.0, "r2": 0.4, "K2": 80.0, "alpha12": 0.003, "alpha21": 0.002, "X0": 10.0, "Y0": 10.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: ChinaModelParameters
description: "Two-component population / resource-competition model (China.java).\n
  \ dX/dt = r1\xB7X\xB7(1 - X/K1) - alpha12\xB7X\xB7Y\n  dY/dt = r2\xB7Y\xB7(1 - Y/K2)
  - alpha21\xB7X\xB7Y\n"
type: object
required:
- r1
- K1
- r2
- K2
- alpha12
- alpha21
- X0
- Y0
properties:
  r1:
    type: number
    description: Growth rate species 1
  K1:
    type: number
    minimum: 0
    description: Carrying capacity species 1
  r2:
    type: number
    description: Growth rate species 2
  K2:
    type: number
    minimum: 0
    description: Carrying capacity species 2
  alpha12:
    type: number
    minimum: 0
    description: Competition effect of 2 on 1
  alpha21:
    type: number
    minimum: 0
    description: Competition effect of 1 on 2
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/o2/china/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/o2/china/schema.yaml)


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
[context.jsonld](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/o2/china/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/o2/china`

