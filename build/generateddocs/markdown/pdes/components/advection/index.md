
# Spatial Advection Operator (Schema)

`mwj.pdes.components.advection` *v0.1*

Linear advection term -v·∇u. Implemented in model.global.Advection.java. Combined with any local kinetic model and diffusion to produce a DIFICI travelling-wave system.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Spatial Advection Operator
**Term:** `-v·∇u`
Implemented in `model.global.Advection.java`. Differential advection between species (v1 ≠ v2) triggers DIFICI travelling waves even when D1 = D2.

## Examples

### DIFICI scenario — differential advection in x
{ "vx": 0.01, "vy": 0.0, "vz": 0.0 }

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: AdvectionOperator
description: "Spatial advection term \u2014 -v\xB7\u2207u"
type: object
properties:
  vx:
    type: number
    description: Advection velocity x-direction [cm/d]
    x-jsonld-id: https://mwj.example.org/pdes/spatial/velocityX
  vy:
    type: number
    description: Advection velocity y-direction [cm/d]
    x-jsonld-id: https://mwj.example.org/pdes/spatial/velocityY
  vz:
    type: number
    description: Advection velocity z-direction [cm/d]
    x-jsonld-id: https://mwj.example.org/pdes/spatial/velocityZ
x-jsonld-prefixes:
  spatial: https://mwj.example.org/pdes/spatial/

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/components/advection/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/components/advection/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "vx": "spatial:velocityX",
    "vy": "spatial:velocityY",
    "vz": "spatial:velocityZ",
    "spatial": "https://mwj.example.org/pdes/spatial/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/components/advection/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/components/advection`

