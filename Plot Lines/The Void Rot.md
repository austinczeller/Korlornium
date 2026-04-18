---
Type: Plot Line
Status: Active
Locations:
  - "[[The Scar]]"
  - "[[Scalecrest Bluffs]]"
  - "[[Frostcrag Glade]]"
  - "[[The Underdark]]"
---

The Void Rot is a spreading corruption originating from the void meteorite sealed beneath [[The Scar]]. As the seal weakens, the rot bleeds into the surrounding world through cracks and fault lines, appearing as purple crystalline growths and dark veins in rock and earth. Creatures exposed to it are twisted and warped. The gibberling infestation at [[Scalecrest Bluffs]] was a direct result of Void Rot seeping up through the earth.

[[Zora Meadowlark]]'s sister, [[Sibil Meadowlark]], is infected. This is one of Zora's primary motivations. [[Ulthite]], a mineral made from the skin of the dead god [[Ulthagos]], resists the spread of Void Rot and is central to Zora's research. [[Gate Stone]]s are also enchanted with Ulthite properties and help keep the rot at bay.

The gnomish community has been mapping void fault lines across [[Korlornium]]. [[Nilah]] the storm dragon had been kept awake for months by gibberlings spawned from a void hole beneath her lair.

The Void itself does not appear to have a will or goal beyond expansion, but something within the meteorite may be directing it.

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
