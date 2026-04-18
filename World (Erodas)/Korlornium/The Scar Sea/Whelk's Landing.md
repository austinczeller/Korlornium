---
dg-publish:
Type: Location
Scale: Place
Location:
  - "[[Thalmyre]]"
Place_Description: Tavern in the population centre of Thalmyre.
Place_Category: Tavern
---

# [[Whelk's Landing]]


## Description
A dive bar, on situated in the isles of [[Thalmyre]], specifically on the island referred to as [[The Seat of Thalmyre]]. It is a neutral ground for the various piracy gangs who inhabit the isles. 
The exterior appears to be a old wooden fishing shack but once inside visitors are greeted by a long set of stairs that are sparsely illuminated by torchlight. The stairs descend below the seafloor and a the tavern sits in a completely glass room within the sea. There is intricate figurines and statues littered from across [[Korlornium]] around the tavern with symbols of a forgotten time. The place is busy and appears to have wealth. The mangey pirates inside starkly contrast the quite sleek interior.


The tavern serves a specialty dish called buttered whelk or sparklefish gumbo.
They carry the finest Dithorian wine and [[Agithian Ale]], it seems like a cultural melting pot and highlights the isles of [[Thalmyre]]. 

The tavern is run by a no-nonsense [[Sea-folk]] woman [[Darla Murdinthe]]. She is well respected across pirate gangs and is known as the matriarch. 
# Menu
- buttered whelk
- sparklefish gumbo
- Rums
- [[Agithian Ale]]
- Dithorian wine

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