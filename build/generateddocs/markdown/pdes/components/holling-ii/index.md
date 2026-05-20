
# Holling Type II Functional Response (Schema)

`mwj.pdes.components.holling-ii` *v0.1*

Saturating Michaelis-Menten (disc equation) response. Implemented in model/lokal/holling/HollingII.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Holling Type II Functional Response
**Formula:** `f(X) = gamma·X / (H + X)`
Saturating response. Used in Scheffer, Plankton, Volterra, Tannentriebwickler models.

## Examples

### Scheffer zooplankton grazing
{ "gamma": 0.4, "H": 0.6 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: HollingTypeIIParameters
description: "f(X) = gamma\xB7X / (H + X) \u2014 saturating response (Michaelis-Menten)"
type: object
required:
- gamma
- H
properties:
  gamma:
    type: number
    minimum: 0
    description: Maximum consumption rate
    x-jsonld-id: https://mwj.example.org/pdes/holling/maxConsumptionRate
  H:
    type: number
    minimum: 0
    description: Half-saturation constant
    x-jsonld-id: https://mwj.example.org/pdes/holling/halfSaturation
x-jsonld-prefixes:
  holling: https://mwj.example.org/pdes/holling/

```

Links to the schema:

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/components/holling-ii/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/components/holling-ii/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "gamma": "holling:maxConsumptionRate",
    "H": "holling:halfSaturation",
    "holling": "https://mwj.example.org/pdes/holling/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/components/holling-ii/context.jsonld)

## Sources

* Holling (1959) Canadian Entomologist 91:293-320

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/components/holling-ii`

