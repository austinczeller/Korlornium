---
Type: Plot Line
Status: Active
Locations:
  - "[[The Scar]]"
  - "[[Heaven's Hole]]"
---

[[Picasso]]'s warlock patron, [[Cthulhu]], has been reaching out through visions and dreams with increasing urgency. In the first vision, [[Sliver]] (Picasso's rat familiar) transformed into a white squid and devoured young [[Tortle]]s before telling Picasso "I AM SO HUNGRY." At [[Heaven's Hole]], Cthulhu forced a WIS save DC 25 to stop Picasso from throwing the [[Gate Stone]] into the depths of the pool.

It is unclear what exactly Cthulhu wants, but the [[Gate Stone]]s and the depths of [[The Scar]] seem to be connected to his desires. This plot line is expected to develop further in upcoming sessions.

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
