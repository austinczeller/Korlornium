---
dg-publish:
Type: Location
Scale: Landmass
Location:
  - "[[Thalmyre]]"
  - "[[The Scar]]"
Place_Description: A small island in the archipelago of Thalmyre home to lots of good fishing
Place_Category: Island
---

# [[Gulper Island]]
## Description
[[Gulper Island]] is a small island in the archipelago of [[Thalmyre]] home to lots of good fishing for the famous [[Sand Gulper]], a fish with particularly tasty meat. The island is inhabited by the pirate crew, [[Gatorpaw Gang]], a middling power among pirates.
This island often sees many visitors from outside [[Thalmyre]] and around [[Korlornium]] for fishing expeditions and charters. 

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
