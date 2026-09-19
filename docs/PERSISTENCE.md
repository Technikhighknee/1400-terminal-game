# Determinism, Persistence, and Replay

## Determinism

The core invariant is:

```
same state
+ same seed
+ same commands
= same future
```

This applies across normal simulation execution and replay.

## Randomness

Never use `Math.random()` inside deterministic simulation logic.

The world owns a persisted root seed.

Randomness should be split into deterministic streams or derived from stable keys such as:

- root seed
- system identifier
- entity identifier
- action ordinal

This prevents unrelated extra random calls from perturbing distant systems.

## Simulation identifiers

Entity, event, and command IDs should be generated deterministically.

## Save contents

A save needs enough information to restore exact simulation behavior.

Conceptually:

- world state snapshot
- scheduler state
- current tick
- root seed / random state
- scenario version
- simulation version
- definition versions
- enabled mod versions
- event log after the snapshot

## Event log

Relevant state-changing events are recorded.

Events should be able to reference causal predecessors.

Example:

```
warehouse burned
← fire spread
← roof ignited
← unattended heat source
```

This enables debugging and historical inspection.

## Snapshots

The event log cannot grow indefinitely without checkpoints.

Periodic canonical snapshots may be written, after which later state can be reconstructed from:

```
snapshot + subsequent events
```

Older event segments may be archived.

## Replay

Replay is primarily an engineering and analysis capability.

It should be possible to:

- load a snapshot
- replay events deterministically
- stop at a chosen event
- inspect entities
- compare world hashes

## Autosave

Autosaves may eventually be configured by:

- real elapsed time
- simulation time
- meaningful state transitions

A save should occur at a deterministic event boundary.

## Schema evolution

Persistent formats require explicit versions.

Save migrations must themselves be deterministic.

A save should record exact scenario and mod versions so incompatible state is not silently loaded.

## Testing

Replay tests should verify that known scenarios produce stable world hashes.

Property and invariant tests should also verify conservation and structural correctness, such as:

- goods do not spontaneously duplicate
- transfers conserve amounts
- ownership shares remain valid
- references remain valid
- events are never scheduled in the past
