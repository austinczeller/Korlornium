---
dg-publish:
Type: Faction
Location:
  - "[[Thalmyre]]"
  - "[[The Scar]]"
---
# [[The Stray Dogs]]
## Description
[[The Stray Dogs]] are a band of pirates led by [[Captain Bubblebeard]], based out of [[Itchy Finger]] — the northernmost island of [[Thalmyre]]. They are unfriendly to outsiders, deeply secretive, and one of the oldest piracy groups in [[Korlornium]].

Their speciality is intelligence and early warning. From the watchtowers and treefort positions on [[Itchy Finger]], they have unobstructed sight lines across the northern approaches to [[The Scar]]. They know what ships are coming before anyone else in the archipelago does, and they sell that information. Captains and gangs who want advance notice of incoming vessels, naval patrols, or rival movements pay the Stray Dogs for it. It is a quiet kind of power — unflashy, essential, and very difficult to undercut.

They are one of three represented gangs in the [[The Hydra (Syndicate)]], which they co-founded alongside the [[Murky Bellows]].

What no one outside the gang knows: every member of the Stray Dogs is a [[Werewolf|werewolf]]. Their nocturnal habits and preternatural instincts are put down to discipline and superstition by those who deal with them. The truth is considerably more dangerous. 
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