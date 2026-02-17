---
dg-publish:
Type: Asset
---
# [[Homepage]]


```zoommap
image: z_Assests/Images/Korlornium.png
imageBases:
  - path: z_Assests/Images/Korlornium.png
markers: z_Assests/Images/Korlornium.markers.json
markerLayers:
  - Default
minZoom: 0.25
maxZoom: 8
wrap: false
responsive: false
width: 100%
height: 480px
resizable: false
resizeHandle: native
id: map-mj874wju
view:
  zoom: 0.2500
  centerX: 0.499401
  centerY: 0.500173
```

```calendarium 

```
```button
name Advance Date
type command
action Calendarium: Set Current Date to Next
color orange
```

## !! TO DO !!
- make start and end fc-date for sessions
- Makes some holidays
- Property to make something MOC?
	- Like checkbox. You check it once you think it deserves a MOC. Should this be only locations? likely. We will need to have sections for every note type related to that location. 
	- Requires updating location template. Should there be a MOC template?? 
- Fill in the world map more. 
- Change groups / organizations to factions in all notes
- 

## Welcome to Korlornium

> [! Note]+
> [[0_Campaign Log|Campaign Log]]
> ![[Characters.base#The Salty Bitches]]
### Create

```meta-bind-button
label: New NPC
icon: ""
style: default
class: ""
cssStyle: ""
backgroundImage: ""
tooltip: ""
id: ""
hidden: false
actions:
  - type: templaterCreateNote
    templateFile: z_Assests/Templates/NPC Template.md
    folderPath: NPC's
    fileName: ""
    openNote: true
    openIfAlreadyExists: false

```
```meta-bind-button
label: New Session
icon: ""
style: default
class: ""
cssStyle: ""
backgroundImage: ""
tooltip: ""
id: ""
hidden: false
actions:
  - type: templaterCreateNote
    templateFile: z_Assests/Templates/Session Template.md
    folderPath: Sessions
    fileName: ""
    openNote: true
    openIfAlreadyExists: false

```
```meta-bind-button
label: New Location
icon: ""
style: default
class: ""
cssStyle: ""
backgroundImage: ""
tooltip: ""
id: ""
hidden: false
actions:
  - type: templaterCreateNote
    templateFile: z_Assests/Templates/Location Template.md
    folderPath: World (Erodas)
    fileName: ""
    openNote: true
    openIfAlreadyExists: false

```
```meta-bind-button
label: New Group/ Organization
icon: ""
style: default
class: ""
cssStyle: ""
backgroundImage: ""
tooltip: ""
id: ""
hidden: false
actions:
  - type: templaterCreateNote
    templateFile: z_Assests/Templates/Group Template.md
    folderPath: /
    fileName: ""
    openNote: true
    openIfAlreadyExists: false

```
```meta-bind-button
label: New Event/ History
icon: ""
style: default
class: ""
cssStyle: ""
backgroundImage: ""
tooltip: ""
id: ""
hidden: false
actions:
  - type: templaterCreateNote
    templateFile: z_Assests/Templates/History Template.md
    folderPath: /
    fileName: ""
    openNote: true
    openIfAlreadyExists: false

```
## Sessions
![[Session.base]]
## Ideas Pads
[[Plot Ideas]]
[[NPC Ideas]]
[[Session Ideas]]
## Recently Updated Articles
![[Recently Updated.base]]
## Databases
>[! Note]-
>To best explore databases change the view

### NPCs 
![[Characters.base]]
### Locations
![[Locations.base#All]]
### Groups
![[Groups.base]]




## End of page