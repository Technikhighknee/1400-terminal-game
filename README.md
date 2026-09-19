# 1400 Terminal Game

A historically grounded, systemic medieval economic role-playing simulation set in the Hanseatic world around the year 1400.

The project is intended to run as a high-quality terminal user interface powered by Node.js and terminal-kit. The simulation is designed bottom-up: people, households, businesses, goods, contracts, buildings, transport, institutions, law, information, and political structures exist as concrete parts of the world rather than as abstract bonuses or scripted events.

The player controls a dynasty rather than a single immortal character. Individual members and employees may be directly controlled or left autonomous, but they remain subject to the same physical, social, legal, informational, and economic rules as NPCs.

No implementation has been committed yet. This repository currently records the design and simulation architecture before development begins.

## Core direction

- Hanseatic region around 1400
- Historically grounded where evidence exists
- Explicit distinction between attested, reconstructed, and systemically completed historical data
- Whole scenario region simulated continuously
- 10-minute simulation time base with pausing and acceleration
- Deterministic simulation with a persisted seed
- Bottom-up economy and production
- Individually simulated people and animals
- Local knowledge instead of omniscient actors or UI
- Physical transport of people, goods, letters, and information
- Concrete ownership, contracts, debt, taxation, law, and institutions
- Systemic events instead of a traditional random-event generator
- Open-ended dynasty play without a mandatory victory condition
- Fully terminal-based interface

## Documentation

- [Vision](docs/VISION.md)
- [Design principles](docs/DESIGN_PRINCIPLES.md)
- [World and simulation model](docs/SIMULATION_MODEL.md)
- [Architecture](docs/ARCHITECTURE.md)
- [Components](docs/COMPONENTS.md)
- [Systems](docs/SYSTEMS.md)
- [Knowledge and information](docs/KNOWLEDGE.md)
- [Historical model](docs/HISTORICAL_MODEL.md)
- [Scenario and data model](docs/SCENARIOS_AND_DATA.md)
- [Determinism, persistence, and replay](docs/PERSISTENCE.md)
- [Terminal UI](docs/TERMINAL_UI.md)
- [Development roadmap](docs/ROADMAP.md)

## Status

Design phase. The simulation model and architecture are being defined before implementation.
