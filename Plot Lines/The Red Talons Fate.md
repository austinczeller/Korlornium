---
Type: Plot Line
Status: Active
Locations:
  - "[[Frostcrag Glade]]"
  - "[[Thalmyre]]"
  - "[[Saugeo]]"
---

The Red Talons were a morally gray crew of pirates led by [[Varnak]] the Red, a Tiefling who raised [[Vel'Korr]] from infancy. The crew had a strict code: steal only from the rich, the corrupt, or the unjust. They were destroyed when they accepted a bounty to kill the elven sorcerer [[Viros]], who had been kidnapping and experimenting on people from [[Frostcrag Glade]].

[[Viros]] lured the crew into a trap. A magical storm wrecked their ship, a tentacled creature dragged it under, and fireballs from Viros' tower killed most of the survivors. Of the twenty crew, only five made it to shore. By the time the dust settled, [[Varnak]] was dead, impaled on debris, and the wizard [[Joanos]] was crippled. [[Vel'Korr]] awoke alone on the rocks with [[Beak]] in his hands and Viros still alive.

Vel'Korr received only half the bounty from Frostcrag Glade, as Viros survived and escaped. He has been haunted by the loss ever since, dulling the pain for years before pulling himself back together and beginning to assemble a new crew.

[[Viros]] is expected to appear in [[Thalmyre]], setting the stage for a long-awaited confrontation. A courier from [[Frostcrag Glade]] arrived in [[Stormveil]] during Session 18, suggesting things are moving in that direction.

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
