
<%*
let filetype = await tp.system.suggester(
  ["Standard", "Location", "NPC", "Faction", "History/Event", "Session", "Item", "Plot Line", "God", "Species"],
  ["Standard", "Location", "NPC", "Faction", "History/Event", "Session", "Item", "Plot Line", "God", "Species"],
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
  template = "[[Faction Template]]";
  await tp.file.move("Factions/" + tp.file.title);

} else if (filetype === "Plot Line") {
  template = "[[Plot Line Template]]";
  await tp.file.move("Plot Lines/" + tp.file.title);

} else if (filetype === "God") {
  template = "[[God Template]]";
  await tp.file.move("Gods/" + tp.file.title);

} else if (filetype === "Species") {
  template = "[[Species Template]]";
  await tp.file.move("Species/" + tp.file.title);
}

if (template !== "") {
  tR += await tp.file.include(template);
}
%>
