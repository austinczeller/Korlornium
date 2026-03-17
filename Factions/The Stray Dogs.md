---
dg-publish:
Type: Group
Location:
  - "[[Thalmyre]]"
  - "[[The Scar]]"
---
# [[The Stray Dogs]]
## Description
[[The Stray Dogs]] are a band of pirates led by [[Captain Bubblebeard]] based out of [[Thalmyre]]. This band of pirates are unfriendly to outsiders, secretive, and are all [[Werewolf|werewolves]]

They are one of three represented gangs apart of the [[The Hydra (Syndicate)]]. [[The Stray Dogs]] and the [[Murky Bellows]] founded this alliance and still remain. 

They are one of the oldest piracy groups in [[Korlornium]]. 
Legend states the founding captain, [[Sterrak Gauge]], befriended a stray dog who nursed him back to health after he was abandoned by his former crew. Once recovered and fueled by vengeance the two of them sought after his old crew, single handedly sinking their ship and killing everyone onboard. [[Sterrak Gauge]] went on to become the most fearsome pirate in [[The Scar]], coveting valuable treasures. Nobody knows for certain when or where he died but legend has it that he and his dog retreated underground somewhere on the isle [[Thalmyre]].

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