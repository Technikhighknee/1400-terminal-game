# Simulation Model

## Time

The base simulation interval is 10 in-game minutes.

Time can be:

- paused
- accelerated
- advanced by scheduled events where no intermediate update is causally necessary

The simulation should not scan every entity every 10 minutes.

## Event-driven execution

Processes schedule their next relevant change.

Examples:

- a person finishes sleeping
- bread finishes baking
- a ship reaches a waypoint
- a payment becomes due
- a market opens
- a disease changes phase

Long intervals may be skipped when no relevant state transition occurs.

## Lazy continuous state

Slow-changing values should be materialized only when needed.

Examples:

- hunger
- thirst
- fatigue
- spoilage
- crop growth
- disease progression
- interest
- wear

Store:

- previous value
- last update tick
- rate or phase

and derive the current value from elapsed time.

## Spatial model

The world is hierarchical.

Typical structure:

```
scenario region
└─ settlement / countryside
   └─ parcel / road / terrain
      └─ building
         └─ room
            └─ container
               └─ object
```

Movement occurs through actual routes and connections.

Cities may physically change through:

- construction
- demolition
- street changes
- harbor changes
- parcel division
- land-use change

## People

Every person in the fully simulated region is an individual.

People have dynamic:

- needs
- health
- age
- relationships
- memories
- beliefs
- skills
- goals
- obligations
- social status
- employment
- family
- knowledge

Daily routines emerge from actual work, travel, obligations, needs, social activity, and events.

## Households

Households consume actual stored goods.

They may own or use:

- homes
- goods
- tools
- money
- land
- businesses

Poverty and welfare should emerge from the same economy rather than from a separate poverty score.

## Businesses

Businesses are economic entities that may possess:

- property
- buildings
- inventories
- employees
- contracts
- debt
- partners
- multiple locations

Business size should be limited by coordination, information, capital, logistics, and law rather than an arbitrary cap.

## Goods and objects

A good exists as a concrete object or lot with information such as:

- owner
- possessor
- location
- quantity
- quality
- condition
- origin

Loss, theft, spoilage, damage, storage, and transport all operate on those concrete goods.

## Production

Production consists of actual:

- inputs
- tools
- work steps
- labor
- time
- skill
- conditions

Quality emerges from:

- material quality
- skill
- tools
- process execution

By-products and waste are real outputs.

## Agriculture

Agriculture uses concrete:

- parcels
- soil
- crops
- seed
- rotation
- weather
- labor
- animals

Land ownership, tenancy, obligations, and usage rights are distinct.

## Animals

Animals are individually simulated in the core region.

They have:

- age
- health
- sex
- reproduction
- productivity
- owner
- feeding requirements

## Transport

Travel occurs through an actual transport network:

- roads
- rivers
- sea routes

Vehicles and journeys involve concrete:

- carts
- horses
- ships
- cargo
- crew
- supplies
- condition

Travelers require real food, lodging, and other supplies.

## Weather and environment

Weather affects:

- agriculture
- roads
- shipping
- labor
- temperature
- fire
- supply

Weather should be spatially coherent across the region rather than independently rolled per city.

## Disease

Disease includes:

- transmission
- progression
- care
- work loss
- mortality
- immunity where appropriate

Epidemics emerge from contact structure, movement, environment, immunity, and care.

## Social systems

Status emerges from:

- law
- wealth
- occupation
- origin
- office
- relationships
- privileges
- reputation

Reputation is not global. It is held by actors or institutions.

Relationships are directional.

## Economy

Each city has its own:

- population
- production
- demand
- stock
- prices

Prices emerge from actual:

- offers
- demand
- inventory
- information
- negotiation

There is no authoritative global market price.

## Law and crime

Law is local and concrete.

Crime originates from actual actions.

Enforcement may involve:

- suspicion
- witnesses
- evidence
- arrest
- court
- punishment

Physical possibility and legality are separate. An illegal action remains physically possible.

## Politics and institutions

Political life is carried by actual:

- councils
- offices
- guilds
- patricians
- interest networks
- rulers
- institutions

Political decisions should emerge from real procedures and actors.

## War

Military units consist of real:

- people
- equipment
- supplies

Recruitment, logistics, refugees, economic disruption, command communication, and casualties feed back into the normal world.

## Religion

Religion affects ordinary life through:

- institutions
- holidays
- worship
- obligations
- property
- employment
- charity
- donations
- social expectations

## External world

The complete scenario region is simulated in detail.

Regions beyond it may use aggregate but causally coherent models for:

- population
- production
- demand
- politics
- prices
- migration
- trade flows

When goods or people enter the detailed region, they become concrete simulation entities.
