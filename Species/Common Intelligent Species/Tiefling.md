---
dg-publish: true
Type: Species
---
# Tiefling
[[Tiefling]] are a unique and intriguing race born from the union of mortals, typically [[Human|humans]] or [[Elf|elves]], and extraplanar entities from the lower planes. These beings carry the blood of fiends, demons, or other otherworldly creatures within them, granting them physical traits that mark them as different from most other mortal races. The most recognizable features of a [[Tiefling]] are their horns, which usually protrude from their forehead or atop their head, as well as their long tails, often tipped with a tuft of fur or barbed with a sharp point.

```dataviewjs
dv.header(2, "Notable " + dv.current().file.name);
dv.table(["Location", "Faction"], 
  dv.pages()
    .where(p => (p.Type === "NPC" || p.Type === "PC") && p.Species && dv.array(p.Species).some(s => s && s.path === dv.current().file.path))
    .map(p => [p.file.link, p.Location, p.Faction])
);
```