---
dg-publish:
Type: Location
Scale: Landmass
Location:
  - "[[Erodas]]"
Place_Description: A highly developed isolated tropical continent
Place_Category: Continent
---

# [[Roeanweal]]

## Description


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

