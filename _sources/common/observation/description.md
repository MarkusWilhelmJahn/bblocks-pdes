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
