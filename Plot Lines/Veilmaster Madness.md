---
Type: Plot Line
Status: Complete
---

**Veilmaster Madness** is a plot line centered around [[The 33rd Veil-Master Race]] in [[Stormveil]]. The race was between [[Terrance Highbrow]], an industry-focused outsider from [[Dithoria City]] who proposed opening logging near [[Heaven's Hole]], and [[Numa]], a woman from the Heaven's Hole community who ran to protect their way of life.

The previous Veil-Father, [[Damon Warthelm]], was found dead in the [[Permitting Office of Stormveil]], setting an already tense political climate on edge. Terrance gained quick popularity promising economic growth, while many locals were suspicious of Warthelm's death.

During Terrance's final speech, he cast Enthrall on the crowd and had doppelgangers attempt to assassinate [[Numa]] while framing [[Heaven's Hole]] for the attack. [[The Salty Bitches]] intervened and helped the town conduct a fair election at [[The Soggy Bottom]].

Numa won with [[Rick Augerland]] serving as vice-master, backed by [[The Miller's Union]]. It became clear that [[Zora Meadowlark]] had a hand in orchestrating the attack to destabilize Heaven's Hole and gain access to the area, likely connected to her larger pursuit of the [[Gate Stone]]s. Terrance was revealed to have a warlock pact tied to Zora or a related entity.

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
