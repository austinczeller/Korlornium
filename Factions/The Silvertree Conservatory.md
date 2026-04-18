---
dg-publish:
Type: Faction
Location:
  - "[[Wyegate]]"
---
# [[The Silvertree Conservatory]]
## Description
[[The Silvertree Conservatory]] is a school for half-[[Elf]]s to teach them the proper Elven culture.
The school is located in the country-side of [[Wyegate]].


## Members
```dataview
TABLE Species,Faction, Location, Type

WHERE Type= "NPC" and contains(Faction, this.file.link)
SORT file.mtime DESC
```
## Related Articles
```dataview
TABLE Type   
WHERE contains(file.outlinks, this.file.link)
AND file.name != this.file.name
```