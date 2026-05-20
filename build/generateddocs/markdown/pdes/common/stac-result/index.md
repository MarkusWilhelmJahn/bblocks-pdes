
# Simulation Result STAC Item (Schema)

`mwj.pdes.common.stac-result` *v0.1*

STAC 1.0 Item cataloguing outputs of any simulation run from FiniteDifferenceMethod4PDES, with plankton-rda extension for model-specific searchable properties.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Simulation Result STAC Item

Generic **STAC 1.0 Feature** for any model run in FiniteDifferenceMethod4PDES.
Uses the `mwj-pdes` extension namespace (prefix → `https://mwj.example.org/pdes/stac/`).

## Key extension properties

| Property | Description |
|---|---|
| `mwj-pdes:model` | Human-readable model name |
| `mwj-pdes:modelClass` | Java class (e.g. `model.lokal.o2.Lorenz`) |
| `mwj-pdes:solver` | `jEuler` / `jRungeKutta` / `jButcher` |
| `mwj-pdes:dimensions` | 0 (ODE) / 1 / 2 / 3 (PDE) |
| `mwj-pdes:scenario` | Qualitative run label |
| `mwj-pdes:provenance` | → PROV `SimulationRun` (`prov:wasDerivedFrom`) |
| `mwj-pdes:observation` | → SOSA `ObservationCollection` (`prov:used`) |

## Context note

`mwj-pdes:provenance` maps to `prov:wasDerivedFrom` and `mwj-pdes:observation`
maps to `prov:used` via the context. The prefix `mwj-pdes` expands all other
extension properties automatically — no individual bindings needed.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: SimulationResultSTACItem
type: object
required:
- type
- stac_version
- id
- geometry
- bbox
- properties
- links
- assets
properties:
  type:
    const: Feature
  stac_version:
    const: 1.0.0
  stac_extensions:
    type: array
    items:
      type: string
  id:
    type: string
  geometry:
    type: object
  bbox:
    type: array
    items:
      type: number
    minItems: 4
  properties:
    type: object
    required:
    - datetime
    properties:
      datetime:
        type: string
        format: date-time
      start_datetime:
        type: string
        format: date-time
      end_datetime:
        type: string
        format: date-time
    patternProperties:
      ^mwj-pdes:model$:
        type: string
        description: Human-readable model name
      ^mwj-pdes:modelClass$:
        type: string
        description: Java class name (e.g. model.lokal.o2.Scheffer)
      ^mwj-pdes:solver$:
        type: string
        enum:
        - jEuler
        - jRungeKutta
        - jButcher
        description: Numerical solver used
      ^mwj-pdes:dimensions$:
        type: integer
        enum:
        - 0
        - 1
        - 2
        - 3
        description: 'Spatial dimensionality: 0=ODE, 1/2/3=PDE'
      ^mwj-pdes:scenario$:
        type: string
        description: Qualitative run label
      ^mwj-pdes:provenance$:
        type: string
        description: URI of the PROV SimulationRun Activity
      ^mwj-pdes:observation$:
        type: string
        description: URI of the SOSA ObservationCollection
  links:
    type: array
    items:
      type: object
      required:
      - href
      - rel
      properties:
        href:
          type: string
        rel:
          type: string
        type:
          type: string
        title:
          type: string
  assets:
    type: object
    additionalProperties:
      type: object
      required:
      - href
      - type
      properties:
        href:
          type: string
        type:
          type: string
        title:
          type: string
        roles:
          type: array
          items:
            type: string
x-jsonld-extra-terms:
  mwj-pdes:provenance:
    x-jsonld-type: '@id'
  mwj-pdes:observation:
    x-jsonld-type: '@id'
x-jsonld-prefixes:
  prov: http://www.w3.org/ns/prov#
  dcat: http://www.w3.org/ns/dcat#
  mwj-pdes: https://mwj.example.org/pdes/stac/

```

Links to the schema:

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/common/stac-result/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/common/stac-result/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "mwj-pdes:provenance": {
      "@type": "@id"
    },
    "mwj-pdes:observation": {
      "@type": "@id"
    },
    "prov": "http://www.w3.org/ns/prov#",
    "dcat": "http://www.w3.org/ns/dcat#",
    "mwj-pdes": "https://mwj.example.org/pdes/stac/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/common/stac-result/context.jsonld)

## Sources

* [STAC 1.0](https://stacspec.org/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/common/stac-result`

