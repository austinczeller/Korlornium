---
Type: Location
Location:
  - "[[The Scar]]"
  - "[[Thalmyre]]"
Place_Description: Northernmost isle of Thalmyre; a narrow watchtower island home to The Stray Dogs
Location_Category: Island
---

# [[Itchy Finger]]

## Description

[[Itchy Finger]] is the northernmost island of [[Thalmyre]] — a long, narrow strip of land running north to south, its tip pointed into open water like a warning. It is the first thing ships from the north encounter when approaching the archipelago, and the [[The Stray Dogs]] have made that geography their entire business.

The island is covered in palms, and among them the Stray Dogs have built an informal network of watchtowers and treefort positions — lashed timber platforms, rope walkways, and elevated lookout posts that give an unobstructed view across the northern approaches to [[The Scar]]. There is no official settlement, no named port. What there is, is eyes.

## The Stray Dogs

[[The Stray Dogs]] run [[Itchy Finger]] as an intelligence and early warning operation. They know what is coming before anyone else in [[Thalmyre]] does — who, how many, flying what colours, riding what tide. This information is their primary trade. Gangs and captains who want advance notice of incoming ships, naval patrols, or rival movements pay the Stray Dogs for the privilege. Those who don't pay hear about things after they happen.

The Dogs are scrappy, secretive, and deeply unfriendly to strangers. Visitors to the island are rare and not encouraged. The watchtowers are not for show — they are manned at all hours, and the crew below is always within earshot.

What no one outside the gang knows is that the Stray Dogs are [[Werewolf|werewolves]] to a person. Their nocturnal vigils and unsettling instincts are attributed to superstition and discipline. The truth is considerably more dangerous.

## Places Within 
```dataview
TABLE Location_Category,Location,Place_Description 
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
