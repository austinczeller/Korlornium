---
dg-publish:
Type: Location
Scale: Landmass
Location:
  - "[[The Scar]]"
  - "[[Thalmyre]]"
Place_Description: A medium sized island in the south east region of Thalmyre
Place_Category: Island
---

# [[Paradise]]

## Description
A medium sized island in the south east region of [[Thalmyre]] home to the piracy gang [[Rumskinners]]. There is a luxury resort called the [[Plaza de Roma]], a popular all-inclusive for wealthy powerful elites across [[Korlornium]], mainly from [[Dithoria City]] and [[Cragbrook]].

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