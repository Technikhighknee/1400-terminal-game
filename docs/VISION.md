# Vision

## What this project is

1400 Terminal Game is an open-ended medieval economic role-playing simulation set in the Hanseatic world around the year 1400.

The simulation focuses on concrete people, households, businesses, goods, property, contracts, transport, institutions, law, information, and social structures. The world should behave as a connected system rather than as a collection of isolated gameplay mechanics.

The player controls a dynasty, including people who work for it. A controlled person may be played directly or left autonomous. Direct control does not grant supernatural knowledge, abilities, or privileges: the character remains bound by the same rules as everyone else.

## Intended experience

The game should support lives such as:

- merchant
- craftsperson
- ship owner
- landlord
- farmer
- lender
- office holder
- guild member
- household head
- employer
- political participant

without turning those roles into separate minigames.

They should emerge from the same simulation.

## Scope

A scenario defines the map and historical setting. Within a scenario, the player chooses a starting city.

The scenario region contains multiple cities and fully simulated surrounding areas. The complete scenario region remains simulated rather than freezing locations that are currently off-screen.

The simulation can continue across generations as long as a plausible controllable successor exists.

There is no mandatory victory condition. The central goal is to inhabit and shape a historical economic and social world.

## Historical ambition

The project should be historically strict where reliable evidence exists.

Historical information is classified as:

- **Attested** — supported by evidence.
- **Plausibly reconstructed** — missing details filled from historically defensible context.
- **Systemically completed** — details required by the simulation but not directly recoverable from sources.

Historical people and initial conditions may be used when evidence is strong enough.

Historical events may enter the world as external conditions, but their local outcomes should not be forced when the simulation can determine them.

## Technical direction

- Node.js
- terminal-kit
- deterministic simulation
- data-driven scenarios
- moddable historical data and rules where practical
- event-driven simulation with periodic updates only where needed
- replayable state evolution
