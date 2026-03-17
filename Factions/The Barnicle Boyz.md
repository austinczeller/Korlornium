---
dg-publish:
Type: Faction
Location:
  - "[[Thalmyre]]"
  - "[[The Scar]]"
---
# [[The Barnicle Boyz]]
## Description
[[The Barnicle Boyz]] are a now disbanded piracy group once apart of the powerful alliance [[The Hydra (Syndicate)]]. They were defeated by the new gang, [[The Rattails]] and most members were killed.

They had a pretty nice beachside estate on the shores of [[Thalmyre]] overlooking [[The Scar]].

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
SORT file.mtime DESC
```