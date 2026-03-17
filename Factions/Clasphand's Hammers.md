---
dg-publish:
Type: Faction
Location:
  - "[[Agite Mountains]]"
  - "[[Duskwind Landing]]"
---

# Clasphand's Hammers
Is an young rag-tag adventuring group led by [[Alain Clasphand]].

Clasphand is the last name they all gave themselves as they did not want to be hunted down from the wizard [[Viros]].

## Members
```dataview
TABLE Species,Faction, Location, Type

WHERE Type= "NPC" and contains(Faction, this.file.link)
SORT file.mtime DESC
```