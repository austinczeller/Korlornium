---
Type: Plot Line
Status: Active
Locations:
  - "[[Driftwood Forest]]"
  - "[[Duskwind Landing]]"
  - "[[Korlornium]]"
---

The gnome community was displaced from [[Driftwood Forest]] when the earthquake triggered by [[Zora Meadowlark]]'s activities in [[Old Duskwind]] destroyed much of the forest. A group of gnomes including [[Melkor Fluffybottom]] and his family were nearly killed. The broader gnome refugee population scattered.

This has been a background thread throughout the campaign. Gnomes have continued to appear at various points, mapping void fault lines and ley lines across [[Korlornium]]. 

There are hints of a larger gnomish migration or exodus underway, though the full picture has not yet emerged.

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
