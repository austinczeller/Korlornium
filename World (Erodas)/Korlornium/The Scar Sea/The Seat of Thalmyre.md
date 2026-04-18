---
dg-publish:
Type: Location
Scale: Landmass
Location:
  - "[[The Scar]]"
  - "[[Thalmyre]]"
Place_Description: A large populated island apart of the archipelago, Thalmyre
Place_Category: Island
---

# [[The Seat of Thalmyre]]

## Description
A large populated island in the archipelago, [[Thalmyre]]. A populated city rests on its northwestern coast, where [[The Murky Bellows]] have established their headquarters.
There is a strong influence of the pirate syndicate, [[The Hydra (Syndicate)]] as well as many other minor piracy gangs. 


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