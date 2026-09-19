# Development Roadmap

The project should be implemented as vertical layers rather than attempting the entire Hanseatic simulation immediately.

## Phase 0 — Deterministic core

Build:

- entity store
- component storage
- commands
- events
- reducers
- scheduler
- simulation time
- deterministic PRNG
- fixed-point utilities
- snapshots
- replay
- world hashing

Goal:

Identical seed and commands produce identical state.

## Phase 1 — Space and objects

Build:

- spatial containment
- physical properties
- containers
- ownership
- condition
- movement
- taking and placing objects
- transfers

Minimal world:

- person
- room
- chest
- goods lot

## Phase 2 — People

Build:

- person
- body
- agent
- mind
- capabilities

Basic actions:

- move
- eat
- drink
- sleep
- work

Goal:

A person can autonomously produce a minimal daily routine.

## Phase 3 — Knowledge

Build:

- perception
- actor knowledge
- communication
- knowledge-bound UI projection

Goal:

Two people may hold different beliefs about the same world.

## Phase 4 — Households

Build:

- household organizations
- family
- shared stores
- consumption
- work responsibilities

Goal:

A household becomes the first complete social-economic unit.

## Phase 5 — Production

Build:

- goods definitions
- tools
- processes
- quality
- wear
- skills

First production chain:

```
grain → flour → bread → consumption
```

## Phase 6 — Local market

Build:

- offers
- demand
- negotiation
- money
- ownership transfer
- market knowledge

Goal:

Prices emerge from real trades.

## Phase 7 — Businesses

Build:

- business organizations
- employment
- wages
- accounting
- contracts
- credit
- debt

Goal:

A bakery or similar workshop can operate as an independent economic entity.

## Phase 8 — City

Build:

- parcels
- buildings
- rooms
- roads
- markets
- wells
- gates
- warehouses
- workshops

Goal:

A functioning urban economy.

## Phase 9 — Agriculture

Build:

- fields
- soil
- seed
- weather effects
- harvest
- livestock
- feed
- mills

Goal:

The city is supplied by a concrete hinterland.

## Phase 10 — Land transport

Build:

- roads
- carts
- horses
- journeys
- inns
- freight

Goal:

Multiple settlements can exchange goods physically.

## Phase 11 — Shipping

Build:

- ships
- crews
- ports
- sea routes
- weather effects
- cargo
- maintenance

Goal:

Maritime trade becomes possible.

## Phase 12 — Demography

Build:

- birth
- childhood
- aging
- marriage
- household formation
- death
- inheritance
- migration

Goal:

The simulated population can sustain itself across generations.

## Phase 13 — Health

Build:

- injuries
- infection
- disease
- transmission
- care
- mortality
- work loss

## Phase 14 — Society

Build:

- citizenship
- guilds
- apprentices
- journeymen
- masters
- status
- religion
- holidays
- welfare

## Phase 15 — Law

Build:

- crime
- witnesses
- evidence
- arrest
- court
- judgment
- enforcement
- seizure
- insolvency

## Phase 16 — Politics

Build:

- councils
- offices
- interests
- procedures
- privileges
- taxation
- tolls

## Phase 17 — Violence and war

Build:

- combat
- recruitment
- military organization
- logistics
- siege
- refugees

## Phase 18 — Hanseatic networks

Build on everything below:

- long-distance merchants
- commercial networks
- privileges
- Kontor relationships
- merchant companies
- inter-city politics
- major trade flows

The Hanse becomes the result of the simulation rather than an isolated subsystem.

## First meaningful vertical slice

A strong early milestone is:

```
person
→ belongs to household
→ needs food
→ household needs income
→ person works
→ business pays wages
→ market sells bread
→ household buys bread
→ person eats
→ baker needs flour
→ miller needs grain
→ farmer grows grain
```

When that chain works entirely through concrete world state, the core simulation concept has been proven.
