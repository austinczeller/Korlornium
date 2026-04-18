---
Type: Plot Line
Status: Active
Locations:
  - "[[Thalmyre]]"
  - "[[The Scar]]"
  - "[[Whelk's Landing]]"
  - "[[Itchy Finger]]"
---

The Tidemother Gate Stone is the next key [[Zora Meadowlark]] needs. It lies somewhere off the coast of [[Thalmyre]], a pirate port town on [[The Scar]]. Zora has pointed [[The Salty Bitches]] toward Thalmyre, where [[Captain Bubblebeard]] is said to have a clue about its location. A [[Thalmyre]] map will likely be needed to solve the puzzle.

The party arrived just as the Tidescrest Tournament is getting underway and the town is buzzing after the Rattails killed the leader of the Barnicle Boyz. [[Viros]] is also expected to be in Thalmyre, setting the stage for a confrontation with [[Vel'Korr]] and the crew.

## Known Factions in Thalmyre
- [[The Rattails]]
- [[The Barnicle Boyz]] (leaderless)
- [[The Blackwake Company]]
- [[The Drifting Bastards]]

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
