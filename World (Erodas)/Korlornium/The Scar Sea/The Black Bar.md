---
Type: Location
Location_Category: Tavern
Location:
  - "[[The Seat of Thalmyre]]"
Place_Description: Upscale Blackwake Company establishment for wealthy Dithorian clientele
---
# [[The Black Bar]]

The entrance is blocked by an actual bar — a solid beam of lacquered black ironwood, chest height, bolted across the doorframe. There is no handle. Someone inside decides if it lifts.

## Description

[[The Blackwake Company]]'s flagship establishment on [[The Seat of Thalmyre]], The Black Bar caters exclusively to wealthy visitors — primarily [[Dithoria City|Dithorian]] merchants, nobles, and anyone else with enough coin to be considered a person of consequence. During [[Tidescrest]] it fills with spectators who want the atmosphere without the smell.

Inside it is dim, warm, and aggressively tasteful. Linen on every table. Staff in matching dark uniforms who smile with great professionalism and remember every face. The drinks are Dithorian wine, aged spirits, and cocktails with names that mean nothing but cost significantly. The food is small and expensive.

The bar is not a secret — everyone in [[The Seat of Thalmyre]] knows what it is and who it's for. Pirates find it offensive on principle. The [[Blackwake Company]] considers this good branding.

A private back room is available to those the Company wishes to speak with. Being invited there is either a very good sign or a very bad one.

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
