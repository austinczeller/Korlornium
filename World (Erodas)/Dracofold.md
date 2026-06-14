---
Type: Location
Location:
  - "[[Erodas]]"
Location_Category: Continent
Place_Description: Volcanic continent of draconic origin, ruled by the dragon queen
publish: true
---
# [[Dracofold]]

The air above [[Dracofold]] smells of sulfur and hot stone. Columns of smoke rise from dozens of active volcanic peaks across the continent's interior, and the sky is rarely blue — stained instead by ash haze and the silhouettes of circling wings.

## Description

[[Dracofold]] is a vast volcanic continent located northwest of [[Korlornium]]. It is the birthplace of all dragonkind, said to have been born from the crater at the continent's molten heart — a place called the **Cradle of Scales**. The first and greatest of these creations was [[Tiamat]], the mother dragon, who remains the supreme authority over all of [[Dracofold]].

[[Tiamat]]'s rule is absolute. She does not govern through laws but through fear and the promise of obliteration. Chromatic dragons serve as her lieutenants, each controlling a territory and the humanoid populations within it. Those who remain in [[Dracofold]] have made their peace with subjugation — they pay tribute, offer labor, and swear loyalty to their draconic lord in exchange for survival and marginal prosperity. These vassal kingdoms are not without culture or ambition, but all political maneuvering happens beneath the shadow of wings.

Over centuries, many chromatic dragons have fled or been exiled from [[Dracofold]] — too proud to serve [[Tiamat]], too dangerous to tolerate. These rogue dragons have spread across [[Erodas]], settling in remote regions and establishing their own smaller tyrannies. The dragons encountered beyond [[Dracofold]] are almost always these expatriates or their descendants.

## Cinderbloom

The volcanic fissures of [[Dracofold]] produce [[Cinderbloom]], a crystalline mineral of extraordinary value. It is harvested by humanoid labor under brutal conditions and is one of [[Dracofold]]'s most lucrative exports — flowing through [[The Murky Bellows]]' smuggling routes into [[Korlornium]], where it is consumed by the wealthy elite in [[Cragbrook]] and beyond.

The [[Dragonborn]] peoples of [[Dracofold]] once held [[Cinderbloom]] as sacred. For generations they practiced the **Ashen Communion** — a seasonal ritual in which communities gathered to drink diluted Cinderbloom nectar at the close of each season, honoring their draconic ancestry and marking the turning of time. [[Tiamat]] outlawed the practice when she commercialized the harvest. Every crystal drunk in ritual is a crystal not sold. To possess [[Cinderbloom]] without authorization in [[Dracofold]] is now punishable by death.

## Notable Locations

- **The Cradle of Scales** — the volcanic crater at the continent's heart, believed to be the origin point of all dragons. A site of immense geothermal activity and a place of grim pilgrimage for draconic cults.

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
