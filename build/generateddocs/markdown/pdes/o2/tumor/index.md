
# Tumor-Immune Interaction (Schema)

`mwj.pdes.o2.tumor` *v0.1*

Two-component tumor growth and immune response model. Tumor.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Tumor-Immune Interaction

**Equation(s):**
```
dT/dt = r·T·(1-T/K) - k·T·I\ndI/dt = sigma - mu·I + alpha·T·I/(1+beta·T)
```

**Java class:** `model.lokal.o2.Tumor`
**Tags:** o2, oncology, immune-response

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "r": 0.18, "K": 1e9, "k": 1e-9, "sigma": 1.3e4, "mu": 0.0412, "alpha": 0.01245, "beta": 1e-9, "T0": 1e6, "I0": 1e6 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: TumorImmuneParameters
description: "Tumor-immune interaction model:\n  dT/dt = r\xB7T\xB7(1-T/K) - k\xB7T\xB7I
  \  (tumor cells)\n  dI/dt = sigma - mu\xB7I + alpha\xB7T\xB7I/(1+beta\xB7T)  (immune
  cells)\n"
type: object
required:
- r
- K
- k
- sigma
- mu
- alpha
- beta
- T0
- I0
properties:
  r:
    type: number
    minimum: 0
    description: Tumor growth rate [d^-1]
  K:
    type: number
    minimum: 0
    description: Tumor carrying capacity
  k:
    type: number
    minimum: 0
    description: Immune killing rate
  sigma:
    type: number
    minimum: 0
    description: Immune cell influx rate
  mu:
    type: number
    minimum: 0
    description: Immune cell death rate
  alpha:
    type: number
    minimum: 0
    description: Immune stimulation rate
  beta:
    type: number
    minimum: 0
    description: Immune inhibition by tumor
  T0:
    type: number
    minimum: 0
    description: Initial tumor cell count
  I0:
    type: number
    minimum: 0
    description: Initial immune cell count
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/tumor/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/tumor/schema.yaml)


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
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/tumor/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/o2/tumor`

