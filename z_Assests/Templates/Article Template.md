---
dg-publish:
Type:
---
<%*
let title = tp.file.title || await tp.system.prompt("Article Name");
-%>
# [[<% title %>]]
## Description
Placeholder

## Related Articles
```dataview
TABLE Type  
WHERE contains(file.outlinks, this.file.link)
AND file.name != this.file.name
SORT file.mtime DESC
```