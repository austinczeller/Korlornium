---
Type: Faction
Location:
---
<%* let title = tp.file.title || await tp.system.prompt("Article Name"); -%>
# [[<% tp.file.title %>]]

## Members
```dataview
TABLE Status, Location

WHERE Type = "NPC" AND contains(Faction, this.file.link)
SORT file.mtime DESC
```
