---
dg-publish:
Type: Location
Scale:
Location:
Place_Description:
Place_Category:
---

<%* let title = tp.file.title || await tp.system.prompt("Article Name"); -%>
# [[<% title %>]]

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

