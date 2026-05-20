
# Jansen Host-Parasitoid Model (Schema)

`mwj.pdes.o2.jansen` *v0.1*

Jansen (1995) host-parasitoid model with density dependence. Jansen.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Jansen Host-Parasitoid Model

**Equation(s):**
```
dN/dt = lambda·N·exp(-a·P) - N\ndP/dt = N·(1 - exp(-a·P)) - mu·P
```

**Java class:** `model.lokal.o2.Jansen`
**Tags:** o2, host-parasitoid, cycles

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "lambda": 2.0, "a": 0.5, "mu": 0.5, "N0": 10.0, "P0": 1.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: JansenHostParasitoidParameters
description: "Jansen (1995) host-parasitoid model with density dependence:\n  dN/dt
  = lambda\xB7N\xB7exp(-a\xB7P) - N\n  dP/dt = N\xB7(1 - exp(-a\xB7P)) - mu\xB7P\n"
type: object
required:
- lambda
- a
- mu
- N0
- P0
properties:
  lambda:
    type: number
    minimum: 0
    description: Host finite rate of increase
  a:
    type: number
    minimum: 0
    description: Parasitoid search efficiency
  mu:
    type: number
    minimum: 0
    description: Parasitoid survival rate
  N0:
    type: number
    minimum: 0
    description: Initial host density
  P0:
    type: number
    minimum: 0
    description: Initial parasitoid density
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/jansen/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/jansen/schema.yaml)


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
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/jansen/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/o2/jansen`

