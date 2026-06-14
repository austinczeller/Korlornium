---
dg-publish: true
Type: Species
---
# Goblin
Goblins are crafty intelligent creatures who have a love for deceit and mischief. They often regard themselves as [[Alune]]'s favorite children. Although they may seem crude, their civilizations and settlements have a robust political hierarchy. Many believe that their political structure is more sustainable and progressive than many large multi-cultural settlements.

```dataviewjs
dv.header(2, "Notable " + dv.current().file.name);
dv.table(["Location", "Faction"], 
  dv.pages()
    .where(p => (p.Type === "NPC" || p.Type === "PC") && p.Species && dv.array(p.Species).some(s => s && s.path === dv.current().file.path))
    .map(p => [p.file.link, p.Location, p.Faction])
);
```