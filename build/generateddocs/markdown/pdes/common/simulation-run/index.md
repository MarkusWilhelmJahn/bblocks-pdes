
# Simulation Run (PROV) (Schema)

`mwj.pdes.common.simulation-run` *v0.1*

Generic PROV Activity capturing one execution of any local kinetic model in FiniteDifferenceMethod4PDES, optionally extended with spatial operators (Diffusion, Advection).

[*Status*](http://www.opengis.net/def/status): Experimental

## Description

# Simulation Run (PROV)

Generic **`prov:Activity`** for any model execution in FiniteDifferenceMethod4PDES.

## Architecture

The software follows an MVC pattern:
- **Model** — local kinetic classes (`model/lokal/`) + spatial operators (`model/global/`)
- **Numerik** — solvers: `jEuler`, `jRungeKutta`, `jButcher` (`model/numerik/`)
- **View** — plotters: `JPlotter0D/1D/2D`, `VTKPlotter0D/3D` (`view/`)
- **GUI** — `MainPanel`, `MainPanelController`, `Simulator`

## PROV alignment

```
sosa:ObservationCollection ──prov:used──► SimulationRun (prov:Activity)
Parameter set (prov:Entity) ──prov:used──►       │ wasAssociatedWith
                               FiniteDifferenceMethod4PDES (prov:Agent)
                                          prov:wasGeneratedBy
                                    ┌────────────▼────────────┐
                                    │ timeseries-csv           │
                                    │ spatial-field-vtk        │
                                    │ plot-*.png               │
                                    └──────────────────────────┘
                                               │ dcat:landingPage
                                         STAC Item
```

## Concrete model blocks

Each concrete model block (e.g. `mwj.pdes.o2.scheffer`) extends this schema
by adding its specific `parameters` sub-schema.

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: SimulationRun
description: 'A PROV Activity representing one execution of any model in FiniteDifferenceMethod4PDES.
  Concrete model building blocks extend this schema with their specific parameter
  sets.

  '
type: object
required:
- type
- modelClass
- startedAtTime
- endedAtTime
- wasAssociatedWith
- used
- generated
properties:
  type:
    const: SimulationRun
  id:
    type: string
    x-jsonld-id: '@id'
  label:
    type: string
    x-jsonld-id: http://www.w3.org/2000/01/rdf-schema#label
  modelClass:
    type: string
    description: Fully-qualified Java class name of the local kinetic model
    examples:
    - model.lokal.o2.Scheffer
    - model.lokal.o2.Lorenz
    - model.lokal.standard.Logistisch
    x-jsonld-id: https://mwj.example.org/pdes/sim/modelClass
  startedAtTime:
    type: string
    format: date-time
    x-jsonld-id: http://www.w3.org/ns/prov#startedAtTime
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#dateTime
  endedAtTime:
    type: string
    format: date-time
    x-jsonld-id: http://www.w3.org/ns/prov#endedAtTime
    x-jsonld-type: http://www.w3.org/2001/XMLSchema#dateTime
  wasAssociatedWith:
    type: object
    required:
    - id
    - label
    - version
    properties:
      id:
        type: string
        const: https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES
        x-jsonld-id: '@id'
      label:
        type: string
        const: FiniteDifferenceMethod4PDES
        x-jsonld-id: http://www.w3.org/2000/01/rdf-schema#label
      version:
        type: string
      localPath:
        type: string
        const: /Users/markusjahn/Documents/GitHub/FiniteDifferenceMethod4PDES
    x-jsonld-id: http://www.w3.org/ns/prov#wasAssociatedWith
  numericalSolver:
    type: string
    enum:
    - jEuler
    - jRungeKutta
    - jButcher
    description: Solver class used (model.numerik.*)
    x-jsonld-id: https://mwj.example.org/pdes/sim/numericalSolver
  spatialSetup:
    type: object
    description: Present only for PDE runs; absent for pure ODE runs
    properties:
      dimensions:
        type: integer
        enum:
        - 1
        - 2
        - 3
      domain_length_x:
        type: number
      domain_length_y:
        type: number
      domain_length_z:
        type: number
      grid_points_x:
        type: integer
      grid_points_y:
        type: integer
      grid_points_z:
        type: integer
      boundary_condition:
        type: string
        enum:
        - zero-flux
        - periodic
        - dirichlet
      diffusion:
        type: boolean
      advection:
        type: boolean
    x-jsonld-id: https://mwj.example.org/pdes/sim/spatialSetup
  visualisation:
    type: string
    enum:
    - JPlotter0D
    - JPlotter1D
    - JPlotter2D
    - VTKPlotter0D
    - VTKPlotter3D
    description: View class used for output (view.*)
    x-jsonld-id: https://mwj.example.org/pdes/sim/visualisation
  used:
    type: object
    required:
    - observation
    properties:
      observation:
        type: string
      parametersId:
        type: string
    x-jsonld-id: http://www.w3.org/ns/prov#used
  parameters:
    type: object
    description: "Model-specific parameters \u2014 defined in each concrete model
      block"
    x-jsonld-id: http://www.w3.org/ns/prov#used
  generated:
    type: array
    minItems: 1
    items:
      type: object
      required:
      - id
      - type
      - format
      properties:
        id:
          type: string
          x-jsonld-id: '@id'
        type:
          type: string
          enum:
          - timeseries-csv
          - spatial-field-csv
          - spatial-field-vtk
          - plot-0d-png
          - plot-1d-png
          - plot-2d-png
          - plot-3d-vtk
        format:
          type: string
        description:
          type: string
    x-jsonld-reverse: prov:wasGeneratedBy
  stacItem:
    type: string
    x-jsonld-id: http://www.w3.org/ns/dcat#landingPage
x-jsonld-extra-terms:
  SimulationRun: http://www.w3.org/ns/prov#Activity
x-jsonld-prefixes:
  prov: http://www.w3.org/ns/prov#
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  plksim: https://mwj.example.org/pdes/sim/
  xsd: http://www.w3.org/2001/XMLSchema#
  dcat: http://www.w3.org/ns/dcat#

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/common/simulation-run/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/common/simulation-run/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "SimulationRun": "prov:Activity",
    "id": "@id",
    "label": "rdfs:label",
    "modelClass": "plksim:modelClass",
    "startedAtTime": {
      "@id": "prov:startedAtTime",
      "@type": "xsd:dateTime"
    },
    "endedAtTime": {
      "@id": "prov:endedAtTime",
      "@type": "xsd:dateTime"
    },
    "wasAssociatedWith": "prov:wasAssociatedWith",
    "numericalSolver": "plksim:numericalSolver",
    "spatialSetup": "plksim:spatialSetup",
    "visualisation": "plksim:visualisation",
    "used": "prov:used",
    "parameters": "prov:used",
    "generated": {
      "@reverse": "prov:wasGeneratedBy"
    },
    "stacItem": "dcat:landingPage",
    "prov": "http://www.w3.org/ns/prov#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "plksim": "https://mwj.example.org/pdes/sim/",
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "dcat": "http://www.w3.org/ns/dcat#",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://raw.githubusercontent.com/MarkusWilhelmJahn/bblocks-pdes/undefined/build/annotated/pdes/common/simulation-run/context.jsonld)

## Sources

* [W3C PROV-O](https://www.w3.org/TR/prov-o/)
* [FiniteDifferenceMethod4PDES](https://github.com/MarkusWilhelmJahn/FiniteDifferenceMethod4PDES)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/MarkusWilhelmJahn/bblocks-pdes](https://github.com/MarkusWilhelmJahn/bblocks-pdes)
* Path: `_sources/common/simulation-run`

