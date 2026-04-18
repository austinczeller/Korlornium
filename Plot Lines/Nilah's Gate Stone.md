---
Type: Plot Line
Status: Complete
Locations:
  - "[[Scalecrest Bluffs]]"
  - "[[Heaven's Hole]]"
  - "[[Stormveil]]"
---

[[Nilah]] the storm dragon had been tasked with guarding the [[Parsus]] [[Gate Stone]] at her lair in [[Scalecrest Bluffs]]. [[Deepseer Poppy]] had previously stolen the stone from Nilah and brought it to [[Heaven's Hole]], where it shattered. Poppy felt an unnatural compulsion to possess it and feared it was a danger to the community.

[[Zora Meadowlark]] believed the Parsus Gate Stone was hidden somewhere near [[Heaven's Hole]], possibly connected to a chasm portal to the [[Feywild]], and was disappointed by what she found there.

[[The Salty Bitches]] flew to [[Scalecrest Bluffs]] on giant dragonflies, entered Nilah's lair, and found her exhausted and tormented by a gibberling infestation rooted in a void hole beneath the lair. After clearing it out, Nilah, doubting her own judgment, asked the party to take the stone to the pool at Heaven's Hole for safekeeping.

## Key NPCs
```dataview
TABLE Species, Location, Faction
FROM "NPC's" OR "Gods"
WHERE contains(Plot_Lines, this.file.link)
SORT file.name ASC
```

## Sessions
```dataview
TABLE date, Location
WHERE Type = "Session" AND contains(Plot_Lines, this.file.link)
SORT date ASC
```
