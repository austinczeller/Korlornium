---
Type: Faction
Status: Active
Base_of_Operations: "[[Bent Peter]]"
Location:
  - "[[Thalmyre]]"
  - "[[Bent Peter]]"
---
# [[The Drifting Bastards]]

## Overview
[[The Drifting Bastards]] are an eclectic group of misfits turned piracy gang, based on the southern island of [[Bent Peter]]. They fly a flag bearing a **driftwood anchor** — a symbol of being adrift but anchored to nothing and no one. The gang has very little political sway within [[The Hydra (Syndicate)]] and is generally looked down on by the major factions, but their unpredictability makes them dangerous to underestimate.

Their ranks skew toward [[Goblin]]s and [[Kobold]]s, and they have a reputation for chaotic boarding tactics — including flinging kobolds onto enemy decks.

## Goals & Methods
They raid opportunistically with little strategy. Their most notable recent action was an attempted boarding of [[The Salty Bitch]] mid-voyage, using flung kobolds as shock troops, which failed.

## Relationship to the Party
The [[The Salty Bitches]] repelled a Drifting Bastards boarding attempt en route to [[Thalmyre]], nearly killing [[Picasso]] in the process. The Bastards haven't formally retaliated, but there is bad blood.

## Members
```dataview
TABLE Species, Location
WHERE Type = "NPC" AND contains(Affiliation, this.file.link)
SORT file.mtime DESC
```

## Related Articles
```dataview
TABLE Type  
WHERE contains(file.outlinks, this.file.link)
AND file.name != this.file.name
SORT file.mtime DESC
```