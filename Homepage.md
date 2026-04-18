---
dg-publish:
Type: Asset
---
# Homepage


```zoommap
image: z_Assests/Images/Korlornium.png
imageBases:
  - path: z_Assests/Images/Korlornium.png
markers: z_Assests/Images/Korlornium.markers.json
markerLayers:
  - Default
minZoom: 0.1
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

## TO DO 

```meta-bind-button
label: Add Task
icon: "plus"
style: primary
class: ""
cssStyle: ""
backgroundImage: ""
tooltip: ""
id: ""
hidden: false
actions:
  - type: templaterCreateNote
    templateFile: z_Assests/Templates/Add Task.md
    folderPath: z_Assests
    fileName: "_task_temp"
    openNote: false
    openIfAlreadyExists: false

```

```dataview
TASK
FROM "z_Assests/To Do"
WHERE !completed
```

## Welcome to Korlornium

## [[The Salty Bitches]]
> Current Party Level: `= [[The Salty Bitches]].party_level`
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
label: New Faction
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
    templateFile: z_Assests/Templates/Faction Template.md
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
## Stubs
```dataviewjs
const unresolved = app.metadataCache.unresolvedLinks;

const stubMap = {};
for (const [file, links] of Object.entries(unresolved)) {
    for (const link of Object.keys(links)) {
        if (!stubMap[link]) stubMap[link] = [];
        stubMap[link].push(file);
    }
}

const stubs = Object.keys(stubMap);
if (stubs.length === 0) {
    dv.paragraph("*All referenced articles have been written. Impressive.*");
} else {
    const pick = stubs[Math.floor(Math.random() * stubs.length)];
    const sources = stubMap[pick];

    dv.paragraph(`*${stubs.length} unwritten articles in the vault.*`);
    dv.table(
        ["Stub", "Referenced In", "Type"],
        sources.map(f => {
            const path = f.replace(/\.md$/, '');
            const name = path.split('/').pop();
            const page = dv.page(f);
            const type = page?.Type ?? "—";
            return [`[[${pick}]]`, dv.fileLink(path, name), type];
        })
    );
}
```

```meta-bind-button
label: "↺ New Stub"
icon: "refresh-cw"
style: default
hidden: false
actions:
  - type: command
    command: dataview:dataview-force-refresh-views
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
![[Hub.base]]

