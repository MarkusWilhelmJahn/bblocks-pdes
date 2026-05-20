
# Linear ODE (Schema)

`mwj.pdes.standard.linear` *v0.1*

Linear scalar ODE dX/dt = a·X + b. Implemented in Linear.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Linear ODE

**Equation(s):**
```
dX/dt = a·X + b
```

**Java class:** `model.lokal.standard.Linear`
**Tags:** scalar, standard, linear

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "a": -0.1, "b": 1.0, "X0": 0.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: LinearODEParameters
description: "dX/dt = a\xB7X + b"
type: object
required:
- a
- b
- X0
properties:
  a:
    type: number
    description: Linear rate coefficient
  b:
    type: number
    description: Constant forcing term
  X0:
    type: number
    description: Initial value
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/standard/linear/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/standard/linear/schema.yaml)


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
[context.jsonld](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/standard/linear/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/standard/linear`

