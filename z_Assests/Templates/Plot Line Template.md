---
Type: Plot Line
Status: Active
Locations:
---
<%* let title = tp.file.title || await tp.system.prompt("Plot Line Name?"); -%>
# [[<% title %>]]

## Summary


## Key NPCs
```dataview
TABLE Species, Location, Faction
FROM "NPC's" OR "Gods"
WHERE contains(Plot_Lines, this.file.link)
SORT file.name ASC
```

## Sessions
```dataview
TABLE date, Location
WHERE Type = "Session" AND contains(Plot_Lines, this.file.link)
SORT date ASC
```
