
# Initial Observation (SOSA) (Schema)

`mwj.pdes.common.observation` *v0.1*

SOSA ObservationCollection providing initial state variables and control parameters for any model run. resultTime becomes t=0 of the simulation.

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Initial Observation (SOSA)

Generic **SOSA `ObservationCollection`** used as initial conditions for any
model in this register. Each state variable and control parameter is a
separate `sosa:Observation` member, individually typed as a `prov:Activity`
that generates one `sosa:Result` (`prov:Entity`).

## PROV alignment (SSN §6.5)

| Concept | PROV equivalent |
|---|---|
| `sosa:Observation` (each member) | `prov:Activity` |
| `sosa:Sensor` (`madeBySensor`) | `prov:Agent` |
| `sosa:FeatureOfInterest` | `prov:Entity` |
| `sosa:Result` (`hasResult`) | `prov:Entity` |
| `sosa:usedProcedure` | `prov:used` |

## Examples

### Generic two-variable initial observation
{
  "type": "ObservationCollection",
  "featureOfInterest": {
    "type": "Feature",
    "geometry": { "type": "Point", "coordinates": [9.37, 47.65] },
    "properties": { "name": "Example system" }
  },
  "phenomenonTime": "2024-01-01/2024-01-07",
  "madeBySensor": "https://mwj.example.org/sensor/generic-001",
  "hasMember": [
    {
      "observedProperty": "https://mwj.example.org/obs/stateVariable1",
      "hasResult": { "value": 1.0, "unit": "dimensionless" },
      "resultTime": "2024-01-07T00:00:00Z"
    },
    {
      "observedProperty": "https://mwj.example.org/obs/stateVariable2",
      "hasResult": { "value": 0.5, "unit": "dimensionless" },
      "resultTime": "2024-01-07T00:00:00Z"
    }
  ]
}

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: InitialObservation
description: 'A SOSA ObservationCollection providing initial conditions for a simulation
  run. Each hasMember entry is a sosa:Observation (prov:Activity) generating one sosa:Result
  (prov:Entity) for one sosa:ObservableProperty.

  '
type: object
required:
- type
- featureOfInterest
- phenomenonTime
- madeBySensor
- hasMember
properties:
  type:
    const: ObservationCollection
  featureOfInterest:
    type: object
    required:
    - type
    - geometry
    properties:
      type:
        const: Feature
      geometry:
        type: object
      properties:
        type: object
        properties:
          name:
            type: string
          description:
            type: string
    x-jsonld-id: http://www.w3.org/ns/sosa/hasFeatureOfInterest
  phenomenonTime:
    type: string
    x-jsonld-id: http://www.w3.org/ns/sosa/phenomenonTime
  madeBySensor:
    type: string
    x-jsonld-id: http://www.w3.org/ns/sosa/madeBySensor
  hasMember:
    type: array
    minItems: 1
    items:
      type: object
      required:
      - observedProperty
      - hasResult
      - resultTime
      properties:
        observedProperty:
          type: string
          x-jsonld-id: http://www.w3.org/ns/sosa/observedProperty
          x-jsonld-type: '@id'
        hasResult:
          type: object
          required:
          - value
          properties:
            value:
              type: number
              x-jsonld-id: http://www.w3.org/ns/sosa/hasSimpleResult
            unit:
              type: string
              x-jsonld-id: http://qudt.org/schema/qudt/unit
          x-jsonld-id: http://www.w3.org/ns/sosa/hasResult
        resultTime:
          type: string
          format: date-time
          x-jsonld-id: http://www.w3.org/ns/sosa/resultTime
          x-jsonld-type: http://www.w3.org/2001/XMLSchema#dateTime
        usedProcedure:
          type: string
          x-jsonld-id: http://www.w3.org/ns/sosa/usedProcedure
          x-jsonld-type: '@id'
    x-jsonld-id: http://www.w3.org/ns/sosa/hasMember
x-jsonld-extra-terms:
  ObservationCollection: http://www.w3.org/ns/sosa/ObservationCollection
x-jsonld-prefixes:
  sosa: http://www.w3.org/ns/sosa/
  xsd: http://www.w3.org/2001/XMLSchema#

```

Links to the schema:

* YAML version: [schema.yaml](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/common/observation/schema.json)
* JSON version: [schema.json](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/common/observation/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "ObservationCollection": "sosa:ObservationCollection",
    "featureOfInterest": "sosa:hasFeatureOfInterest",
    "phenomenonTime": "sosa:phenomenonTime",
    "madeBySensor": "sosa:madeBySensor",
    "hasMember": {
      "@context": {
        "observedProperty": {
          "@id": "sosa:observedProperty",
          "@type": "@id"
        },
        "hasResult": {
          "@context": {
            "value": "sosa:hasSimpleResult",
            "unit": "http://qudt.org/schema/qudt/unit"
          },
          "@id": "sosa:hasResult"
        },
        "resultTime": {
          "@id": "sosa:resultTime",
          "@type": "xsd:dateTime"
        },
        "usedProcedure": {
          "@id": "sosa:usedProcedure",
          "@type": "@id"
        }
      },
      "@id": "sosa:hasMember"
    },
    "sosa": "http://www.w3.org/ns/sosa/",
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://markuswilhelmjahn.github.io/bblocks-pdes/build/annotated/pdes/common/observation/context.jsonld)

## Sources

* [W3C SOSA/SSN Ontology](https://www.w3.org/TR/vocab-ssn/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/common/observation`

