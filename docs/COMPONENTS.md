# Components

The design intentionally uses a modest number of broad, composable components rather than hundreds of tiny ECS components.

Components store state. Systems contain behavior.

## Core components

### Identity

General identity and definition references.

Possible fields:

- name
- kind
- tags
- definition ID

### Spatial

Where an entity is located.

Possible fields:

- parent location
- fine position
- jurisdictions

### Physical

Physical properties.

Possible fields:

- mass
- volume
- dimensions
- material composition

### Ownership

Legal ownership and usage.

Possible fields:

- owners and shares
- current possessor
- usage rights

Ownership is distinct from possession.

### Container

Any entity capable of containing other entities.

Used by:

- bags
- chests
- people
- rooms
- warehouses
- carts
- ships

Possible fields:

- contents
- maximum mass
- maximum volume
- access rules

### Condition

Condition of physical objects and lots.

Possible fields:

- quality
- integrity
- wear
- contamination
- creation time
- spoilage or expiry state

### Agent

Entities capable of autonomous decisions or direct player control.

Possible fields:

- control mode
- current action
- delegated tasks
- next decision tick

### Person

Human structural data.

Possible fields:

- birth
- death
- sex
- parents
- spouses
- children
- household

### Body

Physiological state.

Possible fields:

- energy
- hydration
- sleep debt
- fatigue
- warmth
- hygiene
- nutrition
- injuries
- disease
- immunity
- pregnancy

### Mind

Decision-relevant psychological state.

Possible fields:

- personality traits
- motives
- goals
- memories
- relationships
- emotional state
- risk preference

### Capabilities

Learned abilities.

Possible fields:

- skills
- languages
- literacy
- numeracy
- known procedures

### Knowledge

Actor-specific information about the world.

A known fact can carry:

- value
- acquisition time
- source
- reliability
- staleness

### Social

Formal social and legal positioning.

Possible fields:

- memberships
- offices
- legal statuses
- citizenship
- guild status

### Organization

Generic institutional composition.

Possible organization types:

- household
- business
- guild
- city council
- monastery
- church
- merchant company
- military unit
- court

Possible fields:

- members
- roles
- hierarchy
- governance

### Contract

Formal agreements between parties.

Possible fields:

- parties
- clauses
- effective date
- deadlines
- collateral
- witnesses
- state

Used for:

- employment
- apprenticeship
- leases
- loans
- deliveries
- partnerships
- marriage-related agreements
- commercial obligations

### Work

A person's persistent work situation.

Possible fields:

- occupation
- employer
- employment contract
- assignments
- availability

### Process

Generic long-running activity.

Possible uses:

- production
- construction
- negotiation
- litigation
- fire response
- treatment
- combat
- learning
- orders

Possible fields:

- type
- definition
- state
- start
- next step
- participants
- inputs
- outputs
- domain-specific data

### Property

Built or spatial property structures.

Possible types:

- parcel
- building
- room
- road
- bridge
- dock
- wall
- harbor

Possible fields:

- parent property
- connections
- usage
- capacity

### Land

Land-specific state.

Possible fields:

- area
- soil
- fertility
- moisture
- crop
- rotation history
- grazing pressure

### Mobility

Entities capable of travel.

Possible fields:

- mode
- route
- destination
- progress
- departure
- arrival
- speed

### Animal

Animal-specific biology.

Possible fields:

- species
- birth
- sex
- parents
- fertility
- productivity

Health still belongs to `Body`.

### Document

Physical or institutional documents.

Possible fields:

- type
- author
- creation date
- content
- seals
- original/copy relation
- authenticity

Used for:

- letters
- contracts
- accounts
- deeds
- registers
- court records
- wills

### Resource

Natural resource state.

Used for:

- forest resources
- fish
- clay
- stone
- ore
- peat

Possible fields:

- quantity
- quality
- regeneration
- extraction difficulty

### Environment

Local environmental state.

Possible fields:

- temperature
- humidity
- sanitation
- exposure
- precipitation
- fire state

## Typical compositions

### Person

```
Identity
Spatial
Physical
Container
Agent
Person
Body
Mind
Capabilities
Knowledge
Social
Work
```

### Animal

```
Identity
Spatial
Physical
Ownership
Body
Animal
Condition
```

### Goods lot

```
Identity
Spatial
Physical
Ownership
Condition
```

### Building

```
Identity
Spatial
Physical
Ownership
Property
Condition
Container
Environment
```

### Household

```
Identity
Spatial
Ownership
Organization
```

### Business

```
Identity
Spatial
Ownership
Organization
Container
```

### Ship

```
Identity
Spatial
Physical
Ownership
Container
Condition
Mobility
Property
```

### Contract

```
Identity
Contract
Document?
```

A legal agreement and the physical written instrument are conceptually separate.

### Field

```
Identity
Spatial
Ownership
Property
Land
Environment
```

### Process entity

```
Identity
Process
```

Components should be expanded only when a genuinely distinct state domain appears. Depth should primarily come from composition and systems.
