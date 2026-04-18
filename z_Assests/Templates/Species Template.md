---
dg-publish:
Type: Species
Rarity:
---
<%* let title = tp.file.title || await tp.system.prompt("Species Name?"); -%>
# [[<% title %>]]

## Description


## Culture and Society


## Notable Members
```dataview
TABLE Location, Faction
WHERE (Type = "NPC" OR Type = "PC") AND contains(Species, this.file.link)
```
