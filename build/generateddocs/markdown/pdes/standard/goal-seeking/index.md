
# Goal-Seeking Model (Schema)

`mwj.pdes.standard.goal-seeking` *v0.1*

Goal-seeking (target) dynamics dX/dt = r·(Z-X). Implemented in Zielsuchend.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Goal-Seeking Model

**Equation(s):**
```
dX/dt = r·(Z - X)
```

**Java class:** `model.lokal.standard.Zielsuchend`
**Tags:** scalar, standard, control

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "r": 0.3, "Z": 5.0, "X0": 0.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: GoalSeekingParameters
description: "dX/dt = r\xB7(Z - X)"
type: object
required:
- r
- Z
- X0
properties:
  r:
    type: number
    minimum: 0
    description: Adjustment rate [d^-1]
  Z:
    type: number
    description: Target (goal) value
  X0:
    type: number
    description: Initial value
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/standard/goal-seeking/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/standard/goal-seeking/schema.yaml)


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
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/standard/goal-seeking/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/standard/goal-seeking`

