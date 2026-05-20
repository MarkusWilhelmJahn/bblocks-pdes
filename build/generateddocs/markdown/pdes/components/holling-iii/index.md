
# Holling Type III Functional Response (Schema)

`mwj.pdes.components.holling-iii` *v0.1*

Sigmoid response — accelerating at low density, saturating at high. Implemented in model/lokal/holling/HollingIII.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Holling Type III Functional Response
**Formula:** `f(X) = gamma·X² / (H² + X²)`
Sigmoid. Used for fish predation on zooplankton in Scheffer model.

## Examples

### Scheffer fish predation on zooplankton
{ "gamma": 0.4, "H": 5.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: HollingTypeIIIParameters
description: "f(X) = gamma\xB7X\xB2 / (H\xB2 + X\xB2) \u2014 sigmoid functional response"
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
    description: Half-saturation constant (inflection point)
    x-jsonld-id: https://mwj.example.org/pdes/holling/halfSaturation
x-jsonld-prefixes:
  holling: https://mwj.example.org/pdes/holling/

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/components/holling-iii/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/components/holling-iii/schema.yaml)


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
[context.jsonld](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/components/holling-iii/context.jsonld)

## Sources

* Holling (1959) Canadian Entomologist 91:293-320

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/components/holling-iii`

