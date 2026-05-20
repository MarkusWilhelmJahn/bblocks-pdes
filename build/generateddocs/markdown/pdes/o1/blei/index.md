
# Lead Kinetics (Blei) (Schema)

`mwj.pdes.o1.blei` *v0.1*

One-compartment lead (Blei) kinetics model dX/dt = k_in - k_out·X. Implemented in Blei.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Lead Kinetics (Blei)

**Equation(s):**
```
dX/dt = k_in - k_out·X   [X = blood lead concentration µg/dl]
```

**Java class:** `model.lokal.o1.Blei`
**Tags:** o1, toxicokinetics, lead

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "k_in": 0.05, "k_out": 0.02, "X0": 0.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: BleiKineticsParameters
description: "One-compartment lead (Blei) kinetics. dX/dt = k_in - k_out\xB7X where
  X is blood lead concentration.\n"
type: object
required:
- k_in
- k_out
- X0
properties:
  k_in:
    type: number
    minimum: 0
    description: "Lead input rate [\xB5g/dl/d]"
  k_out:
    type: number
    minimum: 0
    description: Lead elimination rate [d^-1]
  X0:
    type: number
    minimum: 0
    description: "Initial blood lead concentration [\xB5g/dl]"
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/o1/blei/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/o1/blei/schema.yaml)


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
[context.jsonld](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/o1/blei/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/o1/blei`

