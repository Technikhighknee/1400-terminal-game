# Design Principles

## Bottom-up over abstract

Prefer concrete causes over aggregate bonuses.

Bad:

```
city food production +20%
```

Preferred:

```
fields
+ seed
+ soil
+ weather
+ labor
+ tools
+ transport
+ storage
= actual food supply
```

## Systemic events over scripted random events

The simulation should not rely on a generic random-event generator for major outcomes.

A famine should emerge from causes such as:

- poor weather
- weak harvests
- depleted stores
- disrupted transport
- price increases
- substitution
- poverty
- malnutrition
- disease
- migration
- mortality

The causes are implemented; the event is observed.

## Same rules for player and NPCs

NPCs and player-controlled people use the same physical, economic, social, legal, and informational systems.

Direct control changes who makes decisions, not what rules apply.

## Local knowledge

Actors only know what they have:

- observed
- experienced
- read
- been told
- inferred

Information has a source, age, and reliability.

The normal UI must obey the same information limits.

## Concrete ownership and movement

Goods, tools, documents, money, vehicles, animals, and people occupy actual locations.

Ownership, possession, access, and usage rights are distinct concepts.

## No magical administration

Business overviews should come from real administrative capability:

- books
- inventories
- reports
- clerks
- messengers
- correspondence

A poorly administered business should produce incomplete or outdated information.

## Delegation instead of simplification

Large organizations remain manageable through:

- roles
- hierarchy
- delegated tasks
- authority
- accounting
- reports
- communication

The world itself is not simplified just because the player's organization grows.

## Determinism

Given:

- identical world state
- identical seed
- identical commands

the simulation must produce the same result.

## Semantic correctness before optimization

Performance optimizations must not change observable simulation semantics.

Aggregation and lazy evaluation are allowed only when they preserve equivalent outcomes.

## Data over hard-coded historical exceptions

Prefer scenario data and rule modules over code such as:

```js
if (city === "Lübeck" && year === 1400) { ... }
```

Historical differences should be represented through data, institutions, law, privileges, geography, and initial state.
