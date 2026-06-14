---
Type: Location
Location:
  - "[[Siroth]]"
Location_Category: City
Place_Description: Capital of Siroth; a port city of stark wealth disparity on the edge of desert and sea
---
# [[Cragbrook]]

The smell of salt and hot sand hits before the city comes into view — then the skyline appears: clay towers of the merchant class rising above the flat, sun-baked rooftops of everyone else, with volcanic peaks smudging the southern horizon.

## Description

[[Cragbrook]] is the capital of [[Siroth]], built where the desert meets the sea. It is a city of contradictions: scorching heat and cool harbor winds, ancient [[Fowlmen]] ruins integrated into modern buildings, and a yawning divide between a wealthy merchant class and the laborers who keep the city running.

The city sits on a natural harbor that made it a key trade hub for the eastern coast of [[Korlornium]]. Its civic administration is nominally a council, but in practice it is captured by a handful of merchant families who fund their own enforcement and write their own exemptions. Among the most profitable of their arrangements is the [[Cinderbloom]] trade — distributed through [[The Murky Bellows]] via [[Thalmyre]], it flows into the city through unofficial channels under the protection of corrupt officials who ensure no questions are asked about its origins. The elite consume it at private gatherings in the upper districts, far from the eyes of the laboring majority.

The volcanic peaks visible from [[Cragbrook]]'s southern edge are distant enough to be scenic and close enough to be ominous.

## Districts

- **[[The Cragfront]]** — the harbor district, loud and commercial, where most legitimate and illegitimate trade enters the city
- **[[The High Shelf]]** — the elevated merchant district built into the cliffs above the harbor, where the wealthiest families maintain their estates
- **[[The Flats]]** — the low-lying majority of the city, where most residents live in cramped, sun-baked conditions with little access to the wealth flowing through the port above

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
