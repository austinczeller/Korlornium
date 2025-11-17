---
dg-publish:
Type: Location
Scale: Settlement
Location:
  - "[[Agite Mountains]]"
Place_Description: Settlement in the foothills of the Agite Mts
Place_Category: Town
---

# [[Saugeo]]

## Description
A western style town resembling the high desert. If ya look at a scoundrel wrong they may challenge you to a [[Quick Draw]].

The town is made up of refugees from a mining disaster in the [[Agite Mountains]] at a site operated by [[Queen Gold]]. 

## Places Within 
```dataview
TABLE Scale,Location,Place_Category, Place_Description 
WHERE Type = "Location" AND contains(Location, this.file.link)
```
 
## Notable NPCs
```dataview
TABLE Location, Species, Organizations
WHERE Type = "NPC" AND contains(Location,this.file.link)
```


## Related Articles
```dataview
TABLE Type  
WHERE contains(file.outlinks, this.file.link)
AND file.name != this.file.name
SORT file.mtime DESC
```