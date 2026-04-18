---
dg-publish:
Type: Faction
Location:
  - "[[Korlornium]]"
party_level: 6
---
# The Salty Bitches

**Party Level:** `VIEW[{party_level}][text]`
```meta-bind-button
label: "▲"
style: primary
actions:
  - type: updateMetadata
    bindTarget: party_level
    evaluate: true
    value: "x + 1"
```
```meta-bind-button
label: "▼"
style: default
actions:
  - type: updateMetadata
    bindTarget: party_level
    evaluate: true
    value: "x - 1"
```
The Salty Bitches are a gang of adventurers who met in [[Duskwind Landing]]. They are crew the vessel, [[The Salty Bitch]] as they sail around [[The Scar]].

## Members PCs
- [[Vel'Korr]]
- [[Faefi]]
- [[Thorne]]
- [[Soffalie]]
- [[Picasso]]
- [[Kel]]
## Members (NPCs)
```dataview
TABLE Species,Faction, Location, Type

WHERE Type= "NPC" and contains(Faction, this.file.link)
SORT file.mtime DESC
```