---
dg-publish:
Type: Faction
Location:
  - "[[Caldrith]]"
---
# The Rellian Dynasty
[[The Rellian Dynasty]] is the power in control of the landmass [[Siroth]] during [[The Divergent War]]. 
The ideals of this group were ones of equality, and to cease the exploitation of [[Siroth]]'s natural resources and magical laylines.


## Members
```dataview
TABLE Species,Faction, Location, Type

WHERE Type= "NPC" and contains(Faction, this.file.link)
SORT file.mtime DESC
```