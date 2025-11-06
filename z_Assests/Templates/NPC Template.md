---
dg-publish:
Alive: true
Type: NPC
Species:
Location:
Organizations:
Antagonisic:
---

---
# <%*
let title = tp.file.title || await tp.system.prompt("NPC Name?");
-%>
# [[<% title %>]]


## Description





## Relationship to party


## Notable Relationships


## Location


## Motives


## Related Articles
```dataview
TABLE Type  
WHERE contains(file.outlinks, this.file.link)
AND file.name != this.file.name
SORT file.mtime DESC
```