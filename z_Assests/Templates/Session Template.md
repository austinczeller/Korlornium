---
dg-publish:
Type: Session
date: 
fc-start: 
fc-end: 
fc-category: Session
Location:
Plot_Lines:
---

# Recap
> 

---

```dataviewjs
const file = app.vault.getAbstractFileByPath(dv.current().file.path);
const cache = app.metadataCache.getFileCache(file);
const headings = (cache?.headings ?? []).filter(h => h.level === 1 && h.heading.startsWith("Scene:"));
if (headings.length > 0) {
    dv.header(4, "Scenes");
    dv.list(headings.map(h => `[[#${h.heading}|${h.heading.replace(/^Scene:\s*/, '')}]]`));
} else {
    dv.paragraph("*No scenes yet.*");
}
```

---

# Notes
*Quick notes during or after session*

>[!info]- Callout Reference
> **Summary** — General scene overview (unfinished thoughts, planning notes)
> **Note** — GM-only info: mechanics, conditions, reminders
> **Description** — Read-aloud scene setting text
> **Challenge** — Non-combat obstacle the party must overcome
> **Combat** — Potential conflict or combat encounter
> **Quote** — Dialogue to read aloud
> **Item** — Items found, given, or relevant

```calendarium

```

```button
name Advance One Day
type command
action Calendarium: Set Current Date to Next
color orange
```

```meta-bind-button
label: "+ Music"
icon: "music"
style: default
hidden: false
actions:
  - type: inlineJS
    code: |
      const { Modal, Setting } = require("obsidian");
      class MusicModal extends Modal {
        constructor(app, cb) {
          super(app);
          this.cb = cb;
          this.urlValue = "";
          this.labelValue = "Music";
        }
        onOpen() {
          this.titleEl.setText("Insert Music");
          new Setting(this.contentEl).setName("YouTube URL")
            .addText(t => t.setPlaceholder("https://youtube.com/watch?v=...").onChange(v => this.urlValue = v));
          new Setting(this.contentEl).setName("Label")
            .addText(t => t.setValue("Music").onChange(v => this.labelValue = v));
          new Setting(this.contentEl)
            .addButton(b => b.setButtonText("Insert").setCta().onClick(() => { this.cb(this.urlValue, this.labelValue); this.close(); }))
            .addButton(b => b.setButtonText("Cancel").onClick(() => this.close()));
        }
        onClose() { this.contentEl.empty(); }
      }
      new MusicModal(app, async (url, label) => {
        if (!url) return;
        const f = app.workspace.getActiveFile();
        const c = await app.vault.read(f);
        await app.vault.modify(f, c + "\n\n![" + (label || "Music") + "](" + url.trim() + ")\n");
      }).open();

```

```meta-bind-button
label: "+ Combat Scene"
icon: "sword"
style: destructive
hidden: false
actions:
  - type: inlineJS
    code: |
      const f = app.workspace.getActiveFile();
      const c = await app.vault.read(f);
      const scene = "\n\n# Scene: [Name]\n\n> [!Summary]+\n> **Stakes:** \n> **Trigger:** \n\n> [!Note]+\n> **Environment/terrain:** \n> **Objective to end encounter:** \n\n> [!Description]+\n> \n\n#### Combatants\n| Name | HP | AC | Init | Notes |\n|------|----|----|----- |-------|\n|      |    |    |      |       |\n|      |    |    |      |       |\n|      |    |    |      |       |\n\n> [!Combat]+\n> **Tactics:** \n> **Abilities/triggers:** \n\n> [!Item]+\n> **Loot:** \n";
      await app.vault.modify(f, c.trimEnd() + scene);

```

```meta-bind-button
label: "+ Social Scene"
icon: "message-circle"
style: primary
hidden: false
actions:
  - type: inlineJS
    code: |
      const f = app.workspace.getActiveFile();
      const c = await app.vault.read(f);
      const scene = "\n\n# Scene: [Name]\n\n> [!Summary]+\n> **Who:** \n> **Their want right now:** \n> **What they'll do to get it:** \n\n> [!Note]+\n> **Party's leverage:** \n> **Pressure on the party:** \n\n> [!Description]+\n> \n\n> [!Challenge]+\n> **If party succeeds:** \n> **If party fails:** \n> **Wild card:** \n\n> [!Quote]+\n> \n";
      await app.vault.modify(f, c.trimEnd() + scene);

```

```meta-bind-button
label: "+ Exploration Scene"
icon: "map"
style: default
hidden: false
actions:
  - type: inlineJS
    code: |
      const f = app.workspace.getActiveFile();
      const c = await app.vault.read(f);
      const scene = "\n\n# Scene: [Name]\n\n> [!Summary]+\n> \n\n> [!Note]+\n> **What can be found:** \n> **What's hidden (DC ):** \n\n> [!Description]+\n> **See:** \n> **Hear:** \n> **Smell/Feel:** \n\n> [!Challenge]+\n> **Hazard or obstacle:** \n> **Skill check:** \n";
      await app.vault.modify(f, c.trimEnd() + scene);

```

---

# Scene: Opening

> [!Summary]+
> 

> [!Note]+
>

> [!Description]+
> 

> [!Challenge]+
> 
