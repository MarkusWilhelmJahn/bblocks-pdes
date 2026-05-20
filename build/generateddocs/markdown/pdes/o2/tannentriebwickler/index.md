
# Larch Budmoth (Tannentriebwickler) (Schema)

`mwj.pdes.o2.tannentriebwickler` *v0.1*

Zeiraphera diniana (larch budmoth) population cycle model. Tannentriebwickler.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Larch Budmoth (Tannentriebwickler)

**Equation(s):**
```
dN/dt = r·N/(1+alpha·N) - beta·N·Q\ndQ/dt = gamma·(Q_max-Q) - delta·N·Q
```

**Java class:** `model.lokal.o2.Tannentriebwickler`
**Tags:** o2, insect-outbreak, 9-year-cycle, Alps

Combined with `model.global.Diffusion` / `model.global.Advection` for PDE runs.
Solved by `jEuler`, `jRungeKutta`, or `jButcher` (model/numerik/).
Output via `JPlotter0D` (ODE), `JPlotter1D/2D` or `VTKPlotter3D` (PDE).

## Examples

### Default parameter set
{ "r": 2.0, "alpha": 0.01, "beta": 0.5, "gamma": 0.3, "delta": 0.1, "Q_max": 1.0, "N0": 0.1, "Q0": 1.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: TannentriebwicklerParameters
description: "Zeiraphera diniana (larch budmoth) cycle model. Larval density (N) oscillates
  with a ~9-year period driven by interplay of tree quality (Q) and parasitism:\n
  \ dN/dt = r\xB7N/(1 + alpha\xB7N) - beta\xB7N\xB7Q\n  dQ/dt = gamma\xB7(Q_max -
  Q) - delta\xB7N\xB7Q\n"
type: object
required:
- r
- alpha
- beta
- gamma
- delta
- Q_max
- N0
- Q0
properties:
  r:
    type: number
    minimum: 0
    description: Budmoth intrinsic growth rate
  alpha:
    type: number
    minimum: 0
    description: Intraspecific competition
  beta:
    type: number
    minimum: 0
    description: Tree quality effect on budmoth
  gamma:
    type: number
    minimum: 0
    description: Tree quality recovery rate
  delta:
    type: number
    minimum: 0
    description: Budmoth effect on tree quality
  Q_max:
    type: number
    minimum: 0
    description: Maximum tree quality
  N0:
    type: number
    minimum: 0
    description: Initial budmoth density
  Q0:
    type: number
    minimum: 0
    description: Initial tree quality
x-jsonld-prefixes:
  plk: https://mwj.example.org/pdes/model/
  prov: http://www.w3.org/ns/prov#

```

Links to the schema:

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/tannentriebwickler/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/tannentriebwickler/schema.yaml)


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
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/o2/tannentriebwickler/context.jsonld)

## Sources

* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/o2/tannentriebwickler`

