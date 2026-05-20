
# Stock-Independent Harvesting (Schema)

`mwj.pdes.o2.harvesting-independent` *v0.1*

Logistic growth with constant (stock-independent) harvest rate H. Bestandsunabhaengige_Ernte.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Stock-Independent Harvesting

**Equation(s):**
```
dX/dt = r·X·(1-X/K) - H
```

**Java class:** `model.lokal.o2.Bestandsunabhaengige_Ernte`
**Tags:** o2, harvesting, constant-quota

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "r": 0.5, "K": 100.0, "H": 5.0, "X0": 50.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: StockIndependentHarvestingParameters
description: "Logistic growth with constant harvest rate H:\n  dX/dt = r\xB7X\xB7(1-X/K)
  - H\n"
type: object
required:
- r
- K
- H
- X0
properties:
  r:
    type: number
    minimum: 0
    description: Intrinsic growth rate [d^-1]
  K:
    type: number
    minimum: 0
    description: Carrying capacity
  H:
    type: number
    minimum: 0
    description: Constant harvest rate
  X0:
    type: number
    minimum: 0
    description: Initial population
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/harvesting-independent/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/harvesting-independent/schema.yaml)


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
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/harvesting-independent/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/o2/harvesting-independent`

