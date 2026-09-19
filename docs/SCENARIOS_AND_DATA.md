# Scenarios and Data

## Scenario meaning

A scenario defines:

- map
- historical setting
- initial date
- settlements
- surrounding countryside
- institutions
- people where known
- law
- political relationships
- routes
- economic starting conditions
- relevant external-world state

The player chooses a starting city inside the selected scenario.

## Data-driven design

Historical and scenario-specific content should live in data rather than general simulation code.

Likely data areas:

```
definitions/
  goods/
  materials/
  tools/
  processes/
  professions/
  skills/
  crops/
  animals/
  diseases/
  injuries/
  coins/
  buildings/
  ships/
  laws/
  privileges/
  offices/
  religions/
  holidays/
  climates/

scenarios/
  <scenario>/
    map/
    settlements/
    people/
    institutions/
    laws/
    economy/
    routes/
    properties/
    history/
    external-world/
```

The exact storage format is not yet fixed.

## Definitions versus entities

Definitions describe reusable types.

Example:

```
rye
density
nutrition
spoilage characteristics
```

An entity describes a concrete runtime instance:

```
Rye lot #19382
412 kg
quality 81
owner: ...
location: ...
harvest origin: ...
```

## Modding

Scenarios and large portions of historical data should eventually be replaceable or moddable.

A mod should not need to modify core code merely to add:

- a good
- profession
- crop
- coin
- local institution
- law
- scenario
- historical person
- building definition
- production process

## Validation

Scenario loading should validate consistency such as:

- referenced entities exist
- routes connect valid locations
- ownership is coherent
- legal jurisdictions exist
- initial inventories are physically possible
- dates are valid
- definition references resolve

## Reconstruction

When detailed historical population or property data is missing, scenario generation may deterministically construct plausible missing detail from historical constraints.

Generated detail must remain distinguishable from attested data.
