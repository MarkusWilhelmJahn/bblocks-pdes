
# Spatial Diffusion Operator (Schema)

`mwj.pdes.components.diffusion` *v0.1*

Fickian diffusion term D·∇²u. Implemented in model.global.Diffusion.java. Combined with any local kinetic model to produce a reaction-diffusion PDE.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Spatial Diffusion Operator
**Term:** `D·∇²u`
Implemented in `model.global.Diffusion.java`. Triggers Turing instability when diffusivity ratio D2/D1 exceeds the critical threshold (~100 for Scheffer model).

## Examples

### Turing scenario (D1 phytoplankton, D2 zooplankton)
{ "D": 1.0e-5 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: DiffusionOperator
description: "Spatial diffusion term \u2014 D\xB7\u2207\xB2u"
type: object
required:
- D
properties:
  D:
    type: number
    minimum: 0
    description: "Diffusion coefficient [cm\xB2/d]"
    x-jsonld-id: https://mwj.example.org/pdes/spatial/diffusionCoefficient
x-jsonld-prefixes:
  spatial: https://mwj.example.org/pdes/spatial/

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/components/diffusion/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/components/diffusion/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "D": "spatial:diffusionCoefficient",
    "spatial": "https://mwj.example.org/pdes/spatial/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/components/diffusion/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/components/diffusion`

