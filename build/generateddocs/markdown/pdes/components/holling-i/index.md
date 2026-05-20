
# Holling Type I Functional Response (Schema)

`mwj.pdes.components.holling-i` *v0.1*

Linear prey consumption proportional to prey density. No handling time. Implemented in model/lokal/holling/HollingI.java.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Holling Type I Functional Response
**Formula:** `f(X) = a·X`
Linear consumption; no saturation. Used as predation term in basic Lotka-Volterra variants.

## Examples

### Default
{ "a": 0.4 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: HollingTypeIParameters
description: "f(X) = a\xB7X \u2014 linear functional response"
type: object
required:
- a
properties:
  a:
    type: number
    minimum: 0
    description: Attack rate (area searched per unit time)
    x-jsonld-id: https://mwj.example.org/pdes/holling/attackRate
x-jsonld-prefixes:
  holling: https://mwj.example.org/pdes/holling/

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/components/holling-i/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/components/holling-i/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "a": "holling:attackRate",
    "holling": "https://mwj.example.org/pdes/holling/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/components/holling-i/context.jsonld)

## Sources

* Holling (1959) Canadian Entomologist 91:293-320

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/components/holling-i`

