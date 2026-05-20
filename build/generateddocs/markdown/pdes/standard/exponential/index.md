
# Exponential Growth (Schema)

`mwj.pdes.standard.exponential` *v0.1*

Single-species exponential growth dX/dt = r·X. Implemented in Exponentiell.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Exponential Growth

**Equation(s):**
```
dX/dt = r·X
```

**Java class:** `model.lokal.standard.Exponentiell`
**Tags:** scalar, standard, growth

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "r": 0.1, "X0": 1.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: ExponentialParameters
description: "dX/dt = r\xB7X"
type: object
required:
- r
- X0
properties:
  r:
    type: number
    description: Growth rate [d^-1]. r>0 growth, r<0 decay.
  X0:
    type: number
    minimum: 0
    description: Initial value
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/standard/exponential/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/standard/exponential/schema.yaml)


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
[context.jsonld](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/standard/exponential/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/standard/exponential`

