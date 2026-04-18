---
dg-publish:
Type: God
Location:
Domain:
Champions:
Gate_Stone:
---
<%* let title = tp.file.title || await tp.system.prompt("God Name?"); -%>
# [[<% title %>]]

## Description


## Worship and Followers


## Notable Relationships


## Lore
```dataview
TABLE Type, Location
WHERE Type = "Event" AND contains(file.outlinks, this.file.link)
```
