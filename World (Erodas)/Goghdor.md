---
Type: Location
Location:
  - "[[Erodas]]"
Location_Category: Continent
Place_Description: A towering fjord rising from the ocean, home to the Star Touched — closer to the heavens than anywhere else on Erodas
aliases:
  - The Reach
publish: true
---
# [[Goghdor]]

Most of [[Goghdor]] is cloud. The mountain is in there somewhere — you can feel it before you see it.

## Description

[[Goghdor]] is not a continent in the traditional sense. It is a single colossal fjord of rock rising from the ocean, closer to [[Korlornium]] than the other distant continents of [[Erodas]], but still remote enough to feel like another world. Its peaks are among the highest points on the planet — so high that those who live near the summit exist above the cloud line, closer to the open sky than any other people on [[Erodas]]. Across [[Erodas]], it is commonly known as **The Reach**.

The lower reaches are perpetually overcast. Thick clouds wrap the mountainside for most of the year, muffling sound, dimming daylight, and making the stars invisible to those who have not yet made the climb. It is cold, damp, and dramatic — waterfalls vanish into grey nothing, and the ocean below is only visible on rare clear days.

## The Star Touched

[[Goghdor]] is home to the **Star Touched** — [[Aasimar]] of both elven and dwarven descent who have built their entire culture around the celestial. They are sparsely spread across the mountainside, living in small communities carved into rock faces and cliff shelters. There is no central government, no unified authority — communities are autonomous, bound together by shared tradition rather than shared rule.

[[Aasimar]] exist elsewhere in [[Erodas]], but they do not call themselves Star Touched. That identity belongs to those raised on [[Goghdor]], shaped by its culture. The divine blood may be the same; the meaning made of it is not.

## The Ascent

Every Star Touched individual makes the climb at least once in their life. The **Ascent** is the defining rite of passage — a journey up [[Goghdor]], through the clouds, to the open sky above. There is no set age, no ceremony of departure. You go when you feel called to go.

At the summit, above the cloud line, the stars are finally visible. The constellations speak — not in words, but in the manifestation of a **[[Skoldrún]]**: an astral spirit in animal form that appears to the climber and does not leave. The Skoldrún is understood to be the gift of the mountain and the stars — a reflection of the climber's purpose, the shape of what they are meant to become.

A Star Touched who has not yet made the Ascent is considered unfinished, not lesser. Those who return are not celebrated loudly — the gift is private. What your Skoldrún is, and what it means, is your own to interpret.

## Skoldrún

The [[Skoldrún]] are constellation spirits — animals of cold light that manifest through the Star Touched's connection to the sky. They take the forms of creatures native to [[Goghdor]] and its waters: mountain goats, hawks, lizards, the occasional deep-sea fish whose constellation appears on the ocean-facing slopes. They are not pets or familiars in a conventional sense. They are more like a second self — present, watchful, and luminous.

Star Touched mages can draw Skoldrún out more deliberately, manifesting them in the world around them or summoning aspects of specific constellations. This magic is not taught so much as uncovered — it emerges from the relationship between the mage and their own Skoldrún over years.

## In Korlornium

[[Goghdor]] is known to the people of [[Korlornium]] — visible on long-range maps, occasionally glimpsed by sailors on clear days — but rarely visited. Those who have returned describe the clouds, the cold, and the unsettling quiet of a place where the sky feels closer than the ground. Star Touched individuals are sometimes encountered in [[Korlornium]], though they are rare enough to draw attention. Their Skoldrún are often the first thing people notice.

## Places Within
```dataview
TABLE Location_Category, Location, Place_Description
WHERE Type = "Location" AND contains(Location, this.file.link)
```

## Notable NPCs
```dataview
TABLE Location, Species, Faction
WHERE (Type = "NPC" OR Type = "PC") AND contains(Location, this.file.link)
```

## Related Articles
```dataview
TABLE Type  
WHERE contains(file.outlinks, this.file.link)
AND file.name != this.file.name
SORT file.mtime DESC
```
