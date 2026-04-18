---
dg-publish:
Type: Location
Scale: Landmass
Location:
  - "[[The Scar]]"
  - "[[Thalmyre]]"
Place_Description: A small island in the archipelago in the central region of Thalmyre
Place_Category: Island
---

# [[Knife Gap]]

## Description

A small island in the archipelago in the central region of [[Thalmyre]]. It serves as a surveillance location for [[The Blackwake Company]] to keep tabs on the gangs in the southern region as well as approaching ships from [[Caldrith]]. [[The Blackwake Company]] has built a draw foot bridge connecting [[The Seat of Thalmyre]] to [[Knife Gap]] for ease of travel by land. They use this bridge as a toll to get to inner islands such as [[Gulper Island]] and [[Paradise]]. The piracy gangs occupying those islands, [[Gatorpaw Gang]] and [[Rumskinners]], don't really like that [[The Blackwake Company]] control this and wish to control that revenue source themselves.
## Places Within 
```dataview
TABLE Scale,Location,Place_Category, Place_Description 
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