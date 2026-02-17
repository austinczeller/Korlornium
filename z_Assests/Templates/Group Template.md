---
Type: Group
Location:
---
<%* let title = tp.file.title || await tp.system.prompt("Article Name"); -%>
# [[<% title %>]]

## Members
```dataview
TABLE Type, Location

WHERE contains(Organizations, this.file.link)
SORT file.mtime DESC
```

## Related Articles
```dataview
TABLE Type  
WHERE contains(file.outlinks, this.file.link)
AND file.name != this.file.name
SORT file.mtime DESC
```