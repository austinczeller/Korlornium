---
dg-publish:
Type: Faction
Location:
  - "[[Korlornium]]"
  - "[[The Scar]]"
  - "[[Frostcrag Glade]]"
---

# The Red Talons
The Red Talons are a piracy crew led by [[Varnak]].
They disbanded after most of the crew was slaughtered by the wizard [[Viros]] in [[Frostcrag Glade]].

## Notable Members
- [[Varnak]]
- [[Torag]]
- [[Joanos]]
- [[Vel'Korr]]
- [[Beak]]
- [[Astra]]
- A [[Fowlmen|Fowlman]]
- 
## Members
```dataview
TABLE Species,Faction, Location, Type

WHERE Type= "NPC" and contains(Faction, this.file.link)
SORT file.mtime DESC
```