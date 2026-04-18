<%*
const task = await tp.system.prompt("New task:");
if (task) {
  const todoFile = app.vault.getAbstractFileByPath("z_Assests/To Do.md");
  const content = await app.vault.read(todoFile);
  await app.vault.modify(todoFile, content + "\n- [ ] " + task);
}
const thisFile = app.vault.getAbstractFileByPath(tp.file.path(true));
setTimeout(() => app.vault.delete(thisFile), 500);
tR = "";
%>