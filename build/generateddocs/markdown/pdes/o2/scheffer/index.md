
# Scheffer Phytoplankton-Zooplankton (RDA) (Schema)

`mwj.pdes.o2.scheffer` *v0.1*

Scheffer (1991) phytoplankton/zooplankton predator-prey model with Holling II/III responses and optional diffusion/advection. Scheffer.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Scheffer Phytoplankton-Zooplankton (RDA)

**Equation(s):**
```
dX1/dt = alpha·N/(HN+N)·X1 - c·X1² - gamma·X1/(H1+X1)·X2 - v1·∇X1 + D1·∇²X1\ndX2/dt = e·gamma·X1/(H1+X1)·X2 - delta·X2 - F·X2²/(H2²+X2²) - v2·∇X2 + D2·∇²X2
```

**Java class:** `model.lokal.o2.Scheffer`
**Tags:** o2, plankton, RDA, Holling-II, Holling-III, Turing, DIFICI

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "alpha":0.5,"c":0.05,"gamma":0.4,"H1":0.6,"H2":5.0,"HN":1.0,"e":0.6,"delta":0.175,"F":0.4,"N":2.5,"D1":1e-5,"D2":2e-3,"X1_0":2.15,"X2_0":2.92,"domain_length_x":100,"grid_points_x":200,"dt":0.1,"t_end":1600,"boundary_condition":"zero-flux" }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: SchefferPlanktonParameters
description: "Scheffer (1991) phytoplankton(X1)/zooplankton(X2) RDA model:\n  dX1/dt
  = alpha\xB7N/(HN+N)\xB7X1 - c\xB7X1\xB2 - gamma\xB7X1/(H1+X1)\xB7X2 - v1\xB7\u2207X1
  + D1\xB7\u2207\xB2X1\n  dX2/dt = e\xB7gamma\xB7X1/(H1+X1)\xB7X2 - delta\xB7X2 -
  F\xB7X2\xB2/(H2\xB2+X2\xB2) - v2\xB7\u2207X2 + D2\xB7\u2207\xB2X2\n"
type: object
required:
- alpha
- c
- gamma
- H1
- H2
- HN
- e
- delta
- F
- N
- D1
- D2
- X1_0
- X2_0
properties:
  alpha:
    type: number
    minimum: 0
    default: 0.5
    description: Max phytoplankton growth rate [d^-1]
  c:
    type: number
    minimum: 0
    default: 0.05
    description: Self-limitation coefficient
  gamma:
    type: number
    minimum: 0
    default: 0.4
    description: Max grazing rate [d^-1] (Holling II)
  H1:
    type: number
    minimum: 0
    default: 0.6
    description: Half-sat grazing [mg.dw/l]
  H2:
    type: number
    minimum: 0
    default: 5.0
    description: Half-sat fish predation [mg.dw/l] (Holling III)
  HN:
    type: number
    minimum: 0
    default: 1.0
    description: Half-sat nutrient uptake
  e:
    type: number
    minimum: 0
    maximum: 1
    default: 0.6
    description: Assimilation efficiency
  delta:
    type: number
    minimum: 0
    default: 0.175
    description: "Zooplankton mortality [d^-1] \u2014 bifurcation param"
  F:
    type: number
    minimum: 0
    default: 0.4
    description: Fish predation [mg.dw/d/l]
  N:
    type: number
    minimum: 0
    default: 2.5
    description: Nutrient level (control)
  D1:
    type: number
    minimum: 0
    default: 1.0e-05
    description: "Phytoplankton diffusivity [cm\xB2/d]"
  D2:
    type: number
    minimum: 0
    default: 1.0e-05
    description: "Zooplankton diffusivity [cm\xB2/d]"
  v1x:
    type: number
    default: 0.0
    description: Phytoplankton advection x [cm/d]
  v2x:
    type: number
    default: 0.0
    description: Zooplankton advection x [cm/d]
  v1y:
    type: number
    default: 0.0
  v2y:
    type: number
    default: 0.0
  X1_0:
    type: number
    minimum: 0
    description: Initial phytoplankton density [mg.dw/l]
  X2_0:
    type: number
    minimum: 0
    description: Initial zooplankton density [mg.dw/l]
  domain_length_x:
    type: number
  domain_length_y:
    type: number
  grid_points_x:
    type: integer
  grid_points_y:
    type: integer
  dt:
    type: number
    minimum: 0
  t_end:
    type: number
    minimum: 0
  boundary_condition:
    type: string
    enum:
    - zero-flux
    - periodic
    - dirichlet
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/scheffer/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/scheffer/schema.yaml)


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
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/scheffer/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/o2/scheffer`

