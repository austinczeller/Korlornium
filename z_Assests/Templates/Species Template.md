<%* -%>
---
dg-publish:
Type: Species
---
<%* let title = tp.file.title || await tp.system.prompt("Species Name?"); -%>
# [[<% title %>]]

## Description


## Culture and Society


```dataviewjs
dv.header(2, "Notable " + dv.current().file.name);
dv.table(["Location", "Faction"], 
  dv.pages()
    .where(p => (p.Type === "NPC" || p.Type === "PC") && p.Species && dv.array(p.Species).some(s => s && s.path === dv.current().file.path))
    .map(p => [p.file.link, p.Location, p.Faction])
);
```
