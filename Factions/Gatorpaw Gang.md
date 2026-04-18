---
Type: Faction
Location:
  - "[[Gulper Island]]"
  - "[[Thalmyre]]"
  - "[[The Scar]]"
---
# [[Gatorpaw Gang]]

## Members
```dataview
TABLE Status, Location

WHERE Type = "NPC" AND contains(Faction, this.file.link)
SORT file.mtime DESC
```

## Description
A middle power pirate gang, specializing in fishing.
They specifically control the trade of the [[Sand Gulper]] a luxury meat in [[Dithoria City]].
Led by their jolly seafaring captain, [[Jorgen "Gary" Jehiamis Fisher]].

## Related Articles
```dataview
TABLE Type  
WHERE contains(file.outlinks, this.file.link)
AND file.name != this.file.name
SORT file.mtime DESC
```