# Architecture

## Core flow

```
Entities
  contain Components

Systems
  inspect Components and world state

Commands
  represent intended actions

Validation
  checks physical and systemic possibility

Events
  represent facts that actually occurred

Reducers
  apply Events to WorldState
```

The terminal UI and autonomous NPC logic both issue commands through the same simulation boundary.

## World state

Conceptually:

```ts
type WorldState = {
  time: SimTime;
  entities: EntityStore;
  scheduler: SchedulerState;
  rng: RandomState;
  scenario: ScenarioRuntime;
  externalWorld: ExternalWorldState;
};
```

## Entities

Anything with independent identity or lifecycle may be an entity.

Examples:

- person
- animal
- goods lot
- tool
- building
- room
- parcel
- cart
- ship
- household
- business
- guild
- council
- monastery
- contract
- document
- court case
- production process
- construction site

Entities are composition-based rather than class-hierarchy based.

## Systems

Systems should remain narrow and domain-specific.

Avoid giant managers such as:

- `CityEconomyManager`
- `PopulationManager`
- `RandomEventManager`
- `GlobalPriceManager`
- `NPCSpawner`

Also avoid monolithic entity methods such as:

- `Person.doEverything()`
- `City.update()`
- `Business.simulate()`

## State mutation

Systems should not directly mutate arbitrary world state.

Preferred flow:

```
system
→ command / validated operation
→ event
→ reducer
→ world state
```

This makes simulation behavior traceable and replayable.

## Event batches

Complex operations may emit atomic batches.

A trade could produce:

- contract concluded
- coins transferred
- goods transferred
- accounting entry written
- observed market information

The batch should either apply completely or not at all.

## Scheduling

The scheduler is a deterministic priority queue.

A scheduled task contains conceptually:

- tick
- priority
- responsible system
- optional entity
- payload

Systems schedule future causal work rather than polling the entire world.

## Tick ordering

Events occurring on the same simulation tick need deterministic ordering.

A possible phase structure:

1. external
2. environment
3. physical
4. biological
5. institutional
6. perception
7. decision
8. action
9. cleanup

Exact phases remain implementation details, but a stable ordering rule is required.

## IDs

Entity and event identifiers should be:

- globally unique within a save
- deterministic
- monotonically or otherwise predictably allocated

Random UUID generation should not participate in core simulation state.

## Numeric representation

Simulation-critical values should use integer or fixed-point representations.

Examples:

- weight
- money
- distance
- probabilities
- shares
- quality

Avoid floating-point drift in deterministic state.

## Derived data

Do not persist data that can be reliably reconstructed.

Examples of typically derived values:

- adult/minor status
- season
- sunrise
- family trees
- market summaries
- total wealth

## Indexes

Large-world queries require indexes.

Likely indexes include:

- components
- spatial containment
- ownership
- organization membership
- contract deadlines
- scheduled processes
- routes
- documents

## Performance rule

Every person may remain individually simulated without being updated constantly.

An agent can have a `nextDecisionTick`.

New information or emergencies can schedule an earlier decision.

This is preferable to simplifying distant people into behaviorally different NPCs.

## Frontend independence

terminal-kit is a rendering and input layer.

The simulation core should not import or depend on terminal-kit.

A different frontend should be possible later without changing simulation semantics.
