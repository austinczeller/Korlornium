---
Type: Faction
Location:
  - "[[Thalmyre]]"
  - "[[The Seat of Thalmyre]]"
---
# [[The Murky Bellows]]
A prominent piracy gang with operations based mainly in [[Thalmyre]]. Founding member of [[The Hydra (Syndicate)]]
Headquarters are based in [[The Seat of Thalmyre]] and hosts many of the population centres 
Led by the infamous captain, [[Gorick 'The Emberstrider' Chambers]]

## Members
```dataview
TABLE Status, Location

WHERE Type = "NPC" AND contains(Faction, this.file.link)
SORT file.mtime DESC
```

## Related Articles
```dataview
TABLE Type  
WHERE contains(file.outlinks, this.file.link)
AND file.name != this.file.name
SORT file.mtime DESC
```