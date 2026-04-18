---
dg-publish:
Type: Location
Scale: Landmass
Location:
  - "[[Thalmyre]]"
  - "[[The Scar]]"
Place_Description: A small island in the archipelago in the southern region of Thalmyre
Place_Category: Island
---

# [[Bent Peter]]

## Description
[[Bent Peter]] is a small island in the southern reaches of [[Thalmyre]]. The [[The Drifting Bastards]] currently occupy the territory.

## Places Within 
```dataview
TABLE Scale,Location,Place_Category, Place_Description 
WHERE Type = "Location" AND contains(Location, this.file.link)
```
 
## Notable NPCs
```dataview
TABLE Location, Species, Faction
WHERE (Type = "NPC" OR Type = "PC") AND contains(Location, this.file.link)
```


## Related Articles
```dataview
TABLE Type  
WHERE contains(file.outlinks, this.file.link)
AND file.name != this.file.name
SORT file.mtime DESC
```
