
# Stock-Dependent Harvesting (Schema)

`mwj.pdes.o2.harvesting-dependent` *v0.1*

Logistic growth with proportional (stock-dependent) harvesting effort. Bestandsabhaengige_Ernte.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Stock-Dependent Harvesting

**Equation(s):**
```
dX/dt = r·X·(1-X/K) - q·E·X\ndE/dt = p·(q·pX·X - c)·E
```

**Java class:** `model.lokal.o2.Bestandsabhaengige_Ernte`
**Tags:** o2, harvesting, bioeconomics, MSY

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "r": 0.5, "K": 100.0, "q": 0.01, "p": 0.1, "pX": 2.0, "c": 0.5, "X0": 50.0, "E0": 10.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: StockDependentHarvestingParameters
description: "Logistic growth with stock-proportional harvesting:\n  dX/dt = r\xB7X\xB7(1-X/K)
  - q\xB7E\xB7X   (stock)\n  dE/dt = p\xB7(q\xB7pX\xB7X - c)\xB7E       (effort)\n"
type: object
required:
- r
- K
- q
- p
- pX
- c
- X0
- E0
properties:
  r:
    type: number
    minimum: 0
    description: Intrinsic growth rate
  K:
    type: number
    minimum: 0
    description: Carrying capacity
  q:
    type: number
    minimum: 0
    description: Catchability coefficient
  p:
    type: number
    description: Profit response coefficient
  pX:
    type: number
    minimum: 0
    description: Unit price of harvested stock
  c:
    type: number
    minimum: 0
    description: Unit cost of fishing effort
  X0:
    type: number
    minimum: 0
  E0:
    type: number
    minimum: 0
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/harvesting-dependent/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/harvesting-dependent/schema.yaml)


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
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/harvesting-dependent/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/o2/harvesting-dependent`

