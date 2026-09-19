# Terminal UI

## Technology

The intended frontend is a full-screen terminal interface built with terminal-kit.

The simulation core remains independent of terminal-kit.

## UI boundary

The UI:

- renders projections of world information
- accepts player input
- issues normal simulation commands

It does not directly mutate simulation state.

## Knowledge-bound presentation

Normal views only display information the dynasty can actually access.

The UI therefore works from a knowledge or administration projection rather than directly exposing objective world state.

## Administration

Detailed management screens may require actual:

- books
- records
- clerks
- reports
- inventories
- correspondence

Information quality should reflect the quality of administration.

## Character control

The player may switch between controllable dynasty members.

The currently active character's:

- location
- knowledge
- capabilities
- legal position

limit direct actions and visible information.

Other controlled people continue autonomously according to delegated responsibilities and their own decision systems.

## Notifications

Notifications must originate from information reaching the dynasty.

There should be no omniscient alert such as:

```
Your warehouse in another city is on fire.
```

unless someone or something actually communicates that fact.

## Auto-pause

Auto-pause rules may respond to events the dynasty knows about.

Examples:

- received urgent letter
- nearby fire discovered
- contract default reported
- family member death learned
- ship arrival observed or reported

## Debug UI

Debug views may reveal objective state and are not part of normal play.

They should support inspection of:

- entities
- components
- event history
- causal chains
- scheduler
- ownership
- relationships
- knowledge
