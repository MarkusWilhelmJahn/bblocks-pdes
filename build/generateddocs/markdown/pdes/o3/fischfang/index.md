
# Fish Harvesting (Fischfang) (Schema)

`mwj.pdes.o3.fischfang` *v0.1*

Three-component fish harvesting model (prey-predator-effort or nutrient-fish-harvest). Fischfang.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Fish Harvesting (Fischfang)

**Equation(s):**
```
dN/dt = r_N - k·N·F\ndF/dt = e·k·N·F - m·F - q·E·F\ndE/dt = p·(q·pF·F - c)·E
```

**Java class:** `model.lokal.o3.Fischfang`
**Tags:** o3, fisheries, bioeconomics, effort-dynamics

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "r_N": 5.0, "k": 0.01, "e": 0.5, "m": 0.1, "q": 0.005, "p": 0.1, "pF": 3.0, "c": 0.5, "N0": 100.0, "F0": 20.0, "E0": 5.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: FischfangParameters
description: "Three-component fish harvesting system (nutrient N, fish F, effort E):\n
  \ dN/dt = r_N - k\xB7N\xB7F\n  dF/dt = e\xB7k\xB7N\xB7F - m\xB7F - q\xB7E\xB7F\n
  \ dE/dt = p\xB7(q\xB7pF\xB7F - c)\xB7E\n"
type: object
required:
- r_N
- k
- e
- m
- q
- p
- pF
- c
- N0
- F0
- E0
properties:
  r_N:
    type: number
    minimum: 0
    description: Nutrient / food input rate
  k:
    type: number
    minimum: 0
    description: Fish feeding rate
  e:
    type: number
    minimum: 0
    maximum: 1
    description: Conversion efficiency
  m:
    type: number
    minimum: 0
    description: Fish natural mortality
  q:
    type: number
    minimum: 0
    description: Catchability coefficient
  p:
    type: number
    description: Effort response to profit
  pF:
    type: number
    minimum: 0
    description: Fish price per unit
  c:
    type: number
    minimum: 0
    description: Cost per unit effort
  N0:
    type: number
    minimum: 0
  F0:
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

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o3/fischfang/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o3/fischfang/schema.yaml)


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
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o3/fischfang/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/o3/fischfang`

