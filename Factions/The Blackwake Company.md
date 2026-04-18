---
Type: Faction
Location:
  - "[[Thalmyre]]"
  - "[[The Scar]]"
---
# [[The Blackwake Company]]

## Members
```dataview
TABLE Status, Location

WHERE Type = "NPC" AND contains(Faction, this.file.link)
SORT file.mtime DESC
```

# [[The Blackwake Company]]

## Description
[[The Blackwake Company]] are a piracy group located on [[The Seat of Thalmyre]] the biggest island in central [[Thalmyre]]. They share the island with [[The Murky Bellows]] but mostly control the southern portion of the island including the isle of [[Knife Gap]].

This group controls much of the [[Spice]] distribution around [[Korlornium]] and the toll bridge connecting [[The Seat of Thalmyre]] to [[Knife Gap]] often used by elites visiting [[Gatorpaw Gang]] and [[Rumskinners]] facilities on either [[Gulper Island]] or [[Paradise]]. 
## Related Articles
```dataview
TABLE Type  
WHERE contains(file.outlinks, this.file.link)
AND file.name != this.file.name
SORT file.mtime DESC
```