---
Type: Plot Line
Status: Active
Locations:
  - "[[The Scar]]"
  - "[[Dithoria City]]"
  - "[[Frostcrag Glade]]"
  - "[[The Underdark]]"
  - "[[Heaven's Hole]]"
---

Breaking the Chain is the overarching plot of the campaign. Long ago, the god [[Dithoria (God)]] sealed himself within a gate beneath [[The Scar]] to contain a void meteorite that had crashed into Erodas. The meteorite carries a corruption known as [[Void Rot]] and the seal has held for ages, but it is weakening. The water covering The Scar, an act of [[Tidemother]], has helped reinforce the seal, but the imbalance is growing. Strange tides, rising sea levels, and spreading void corruption are all symptoms of the gate straining.

[[Zora Meadowlark]], a [[Drow]] necromancer from [[The Underdark]], is working to free Dithoria. Her home beneath the surface has been ravaged by Void Rot, and her sister [[Sibil Meadowlark]] is infected. The Void has told Zora that freeing Dithoria will restore the Underdark, but Zora intends to consume the void seed herself and ascend. She has assembled a team and aligned with underground fundamentalist followers of Dithoria in [[Dithoria City]], who fear their god's power is waning.

To free Dithoria, [[Zora Meadowlark]] needs the [[Gate Stone]]s, divine artifacts made from [[Ulthite]] and guarded by the other gods. Each stone is a key to Dithoria's lock. [[Viros]] is mining Ulthite at [[Frostcrag Glade]] to support the operation. [[Nashirra]] the bone naga serves as Zora's enforcer and messenger.

[[The Salty Bitches]] first became entangled in this plot when Zora's activities in [[Old Duskwind]] caused a massive earthquake. They have since crossed paths with her repeatedly, entered into a tenuous alliance, and are now sailing to [[Thalmyre]] in pursuit of the Tidemother Gate Stone.

## Gate Stones
- [[Ulthagos]] Gate Stone - Held by [[Zora Meadowlark]]
- [[Parsus]] Gate Stone - Recovered from [[Nilah]]'s lair, brought to [[Heaven's Hole]]
- Tidemother Gate Stone - Believed to be near [[Thalmyre]]

## Sub-Plots
- [[Nilah's Gate Stone]]
- [[The Void Rot]]
- [[The Search for Tidemother Gate Stone]]

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
