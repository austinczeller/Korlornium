---
dg-publish: true
Type: Species
---
# Orc
Orcs are hardy tough and large individuals. They are similar to [[Dwarf|dwarves]] as they take pride in craft and muscle. Notable features include small tusks which grow from their lower jaw and pale to dark green complexion.

```dataviewjs
dv.header(2, "Notable " + dv.current().file.name);
dv.table(["Location", "Faction"], 
  dv.pages()
    .where(p => (p.Type === "NPC" || p.Type === "PC") && p.Species && dv.array(p.Species).some(s => s && s.path === dv.current().file.path))
    .map(p => [p.file.link, p.Location, p.Faction])
);
```