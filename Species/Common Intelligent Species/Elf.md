---
dg-publish: true
Type: Species
---
# Elf
Elves are long living humanoid intelligent species. They are one of the most widespread species in [[Korlornium]] alongside [[Human|humans]].

```dataviewjs
dv.header(2, "Notable " + dv.current().file.name);
dv.table(["Location", "Faction"], 
  dv.pages()
    .where(p => (p.Type === "NPC" || p.Type === "PC") && p.Species && dv.array(p.Species).some(s => s && s.path === dv.current().file.path))
    .map(p => [p.file.link, p.Location, p.Faction])
);
```