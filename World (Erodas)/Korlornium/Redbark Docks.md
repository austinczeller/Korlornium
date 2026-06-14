---
Type: Location
Location:
Place_Description:
Location_Category: Port
---

# [[Redbark Docks]]

>[! Note]
> **Scale:** *Continent, Region, Settlement, Landform, Place*
> > [! example]
> > **Title:** The Sunken Sail
> > **Scale:** Place
> > **Location:** Duskwind Landing
> > **Place Description:** Tavern

> [!warning] 
> Reminder to move to appropriate folder:
> Root template saves in /World (Erodas)
## Description
These docks are located on the western shores of the [[The Scar]] on the continent [[Caldrith]] located just outside the town [[Stormveil]]. They are a common shipping dock used to export lumber processed at the [[Stormwood Mill]].
Recently they have seen much more activity through ships coming from [[Duskwind Landing]].

## Places Within 
```dataview
TABLE Location_Category,Location,Place_Description 
WHERE Type = "Location" AND contains(Location, this.file.link)
```
 
## Notable NPCs
```dataview
TABLE Location, Species, Faction
WHERE (Type = "NPC" OR Type = "PC") AND contains(Location, this.file.link)
```


