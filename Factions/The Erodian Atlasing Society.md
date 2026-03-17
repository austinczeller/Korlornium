---
dg-publish: true
Type: Faction
Location:
  - "[[Erodas]]"
---
# The Erodian Atlasing Society
# About the Author(s)
[[The Erodian Atlasing Society]] is a collection of authors who remain anonymous throughout time. We collect and compile particularly interesting histories as they develop across the world of [[Erodas]]. Please do not attempt to contact the society as anonymity is the key to our longevity and impartial reports. Our texts are updated regularly through magical means whenever new historical accounts come to light. We hope you enjoy exploring the rich histories and cultures of [[Erodas]] captured through our publications.

## Members
```dataview
TABLE Species,Faction, Location, Type

WHERE Type= "NPC" and contains(Faction, this.file.link)
SORT file.mtime DESC
```