
<%*
let filetype = await tp.system.suggester(
  ["Standard", "Location", "NPC", "Faction", "History/Event", "Session", "Item"],
  ["Standard", "Location", "NPC", "Faction", "History/Event", "Session", "Item"],
  false,
  "What are you creating?"
);

let template = "";

if (filetype === "Location") {
  template = "[[Location Template]]";
  await tp.file.move("World (Erodas)/" + tp.file.title);

} else if (filetype === "NPC") {
  template = "[[NPC Template]]";
  await tp.file.move("NPC's/" + tp.file.title);

} else if (filetype === "Session") {
  template = "[[Session Template]]";
  await tp.file.move("Sessions/" + tp.file.title);

} else if (filetype === "History/Event") {
  template = "[[History Template]]";
  await tp.file.move("History/" + tp.file.title);

} else if (filetype === "Faction") {
  template = "[[Group Template]]";
  await tp.file.move("Factions/" + tp.file.title);
}

if (template !== "") {
  tR += await tp.file.include(template);
}
%>
# [[<% tp.file.title %>]]

## Description
Placeholder

## Related Articles
```dataview
TABLE Type  
WHERE contains(file.outlinks, this.file.link)
AND file.name != this.file.name
SORT file.mtime DESC
```