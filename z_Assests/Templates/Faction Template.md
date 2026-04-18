---
Type: Faction
Status: Active
Base_of_Operations: 
Leader: 
Allies: 
Enemies: 
Location:
dg-publish:
---
<%* let title = tp.file.title || await tp.system.prompt("Faction Name"); -%>
# [[<% tp.file.title %>]]

## Overview


## Goals & Methods


## Structure


## Relationship to the Party


## Members
```dataview
TABLE Status, Location
WHERE Type = "NPC" AND contains(Affiliation, this.file.link)
SORT file.mtime DESC
```

## Notable Locations
```dataview
LIST
WHERE Type = "Location" AND contains(Faction, this.file.link)
```
