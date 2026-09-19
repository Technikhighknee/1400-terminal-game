# Systems

Systems own behavior, not entities.

The exact implementation may consolidate or split some systems, but the following domains describe the intended responsibilities.

## Core

- Clock
- Scheduler
- Command handling
- Event handling
- deterministic random streams
- entity lifecycle
- indexes

## Space and movement

- spatial containment
- access control
- pathfinding
- movement
- transport
- capacity

## Environment

- weather
- daylight
- temperature
- fire
- sanitation
- decay

## Body and health

- needs
- fatigue
- nutrition
- health
- disease
- injury
- pregnancy
- aging
- death

## Agents

- goals
- utility
- planning
- decisions
- actions
- delegation
- schedules

NPC decisions use:

- needs
- goals
- obligations
- knowledge
- relationships
- personality
- available actions
- risk preference

## Knowledge and communication

- perception
- knowledge update
- conversation
- rumor propagation
- documents
- messages
- reports

## Economy

- ownership
- inventory
- consumption
- markets
- negotiation
- trade
- money
- accounting
- contracts
- credit
- debt
- taxation
- tolls
- employment
- wages

## Production

- production
- quality
- tools
- maintenance

Production operates on concrete:

- goods
- labor
- tools
- time
- process steps

## Construction and infrastructure

- construction
- repair
- buildings
- infrastructure

## Agriculture and natural resources

- crops
- soil
- field work
- harvest
- livestock
- grazing
- forestry
- fishing
- resource extraction

## Household and population

- households
- family
- marriage
- inheritance
- childhood
- migration
- demography

## Skills and professions

- learning
- apprenticeship
- profession
- guild progression

## Society

- status
- citizenship
- reputation
- social influence
- local norms
- welfare
- religion
- calendar

## Law

- laws
- privileges
- crime
- evidence
- investigation
- enforcement
- courts
- punishment
- inheritance law

## Politics

- offices
- councils
- governance
- influence
- elections where historically applicable
- formal decision procedures

## Combat and war

- combat
- morale
- recruitment
- military organization
- military logistics
- siege
- war
- refugees

## Long-distance trade and Hanseatic structures

- merchants
- trade routes
- shipping
- ship operation
- cargo
- ports
- Hanseatic network relationships

The Hanse should not be implemented as an abstract trade bonus. It emerges from merchants, cities, privileges, offices, routes, institutions, and commercial relationships.

## External world

Outside the fully simulated scenario region, aggregate models may maintain:

- population
- production
- consumption
- trade
- migration
- politics
- price conditions

Those models must remain causally compatible with the detailed world.
