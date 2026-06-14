---
dg-publish: true
Type: Species
---
# Drow
Drow are a sub-species of elves which have historically been persecuted and dwelled in societies underground. Their skin is a deep to light purple or blue.
Today drow are common to be found above or below ground in settlements and cities alike. The ancient remains of drow cities have said to be lost with time.

```dataviewjs
dv.header(2, "Notable " + dv.current().file.name);
dv.table(["Location", "Faction"], 
  dv.pages()
    .where(p => (p.Type === "NPC" || p.Type === "PC") && p.Species && dv.array(p.Species).some(s => s && s.path === dv.current().file.path))
    .map(p => [p.file.link, p.Location, p.Faction])
);
```