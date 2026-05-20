
# Holling Type IV Functional Response (Schema)

`mwj.pdes.components.holling-iv` *v0.1*

Inhibition / Monod-Haldane response — unimodal, decreasing at high prey density. Implemented in model/lokal/holling/HollingIV.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Holling Type IV Functional Response
**Formula:** `f(X) = a·X / (b + X + c·X²)`
Monod-Haldane inhibition. Prey can "confuse" or overwhelm predators at high density.

## Examples

### Default inhibition response
{ "a": 0.4, "b": 0.6, "c": 0.1 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: HollingTypeIVParameters
description: "f(X) = a\xB7X / (b + X + c\xB7X\xB2) \u2014 inhibition functional response"
type: object
required:
- a
- b
- c
properties:
  a:
    type: number
    minimum: 0
    description: Maximum rate numerator
    x-jsonld-id: https://mwj.example.org/pdes/holling/maxRate
  b:
    type: number
    minimum: 0
    description: Baseline half-saturation
    x-jsonld-id: https://mwj.example.org/pdes/holling/halfSaturation
  c:
    type: number
    minimum: 0
    description: Inhibition coefficient
    x-jsonld-id: https://mwj.example.org/pdes/holling/inhibitionCoeff
x-jsonld-prefixes:
  holling: https://mwj.example.org/pdes/holling/

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/components/holling-iv/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/components/holling-iv/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "a": "holling:maxRate",
    "b": "holling:halfSaturation",
    "c": "holling:inhibitionCoeff",
    "holling": "https://mwj.example.org/pdes/holling/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/components/holling-iv/context.jsonld)

## Sources

* Holling (1959) Canadian Entomologist 91:293-320

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/components/holling-iv`

