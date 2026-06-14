---
Type: Location
Location_Category: Shop
Location:
  - "[[The Seat of Thalmyre]]"
Place_Description: Weapons shop specialising in explosives and firearms
---
# [[The Blowpipe]]

The smell hits you before the sign does — sulfur, saltpeter, and something sweet that probably shouldn't be sweet.

## Description

A narrow, reinforced shopfront wedged between two taverns on the main drag of [[The Seat of Thalmyre]]. The walls are thick stone — notably thicker than every building around it, and notably more scorched. A hand-painted sign above the door shows a cannon with a pufferfish shooting out.

Inside, the shelves are dense with powder flasks, fuse cord, hand cannons, blunderbusses, and small casks of varying lethality. A back wall holds the specialty stock — bottled fire, compressed charges, and devices with no clear label that the proprietor describes only as *"situational."* Everything is organized, clean, and slightly too close together for comfort.

During [[Tidescrest]] the shop does its best business of the year. Half the fireworks going off in the street came from here.

Although [[The Blowpipe]] is neutral, [[The Rattails]] are enthusiastic customers of their goods.

## Places Within
```dataview
TABLE Location_Category, Location, Place_Description
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
