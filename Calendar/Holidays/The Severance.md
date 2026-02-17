---
dg-publish:
Type: Event
fc-date:
---
# [[The Severance]]
## Description
Placeholder

## Related Articles
```dataview
TABLE Type  
WHERE contains(file.outlinks, this.file.link)
AND file.name != this.file.name
SORT file.mtime DESC
```