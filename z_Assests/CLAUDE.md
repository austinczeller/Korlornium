# Korlornium Campaign Vault

When beginning work please read this document, all info on homepage, AI policy, get familiar with plot lines, and player characters.

This is an Obsidian vault containing DM notes for an ongoing D&D campaign set in the world of Erodas, specifically the region of Korlornium. I am organizing this vault as a Wikipedia inspired database for myself, but also provides the players important lore through the [[General Histories of Korlornium]] and linked pages. The notes (.md files) act as articles within the wiki and should follow similar syntax and style, linking to other articles whenever appropriate. Please try to link generated content to existing articles whenever you can. Names will always be full names when available, although not all characters have a last name.

The current player party is called The Salty Bitches, but will likely come to a close in the next few sessions as the players who play Vel'korr and Faefi are moving. Once they leave I would like to make a new campaign within the same plot lines.

The D&D campaign(s) running are using the 2024 mechanics and may transition into Daggerheart in the future.

Everything we create should fit within the world and make sense within the created plot lines, unless we are generating a completely new plot line.
## AI Policy
See `z_Assests/AI Policy.md`. This applies to all work done in this vault.


## D&D Mechanics
- For specific dungeons and dragons mechanics refer to [[D&D Player Handbook 2024 Edition.pdf]].
- Challenges created by both human and AI will be challenging for an experienced active party at for their party's level. 
- When creating combat prioritize enemy synergies with abilities and think about how terrain, time, or other constraints can be used to further challenge the players.
- The [[Monster Manual.pdf]] contains stat blocks of vanilla D&D monsters refer to the stat blocks found in this pdf when creating combat encounters.
## Vault Conventions
- Notes use `[[WikiLinks]]` for internal linking
- Frontmatter `Type` field categorizes every note — see **Note Types** below
- Folder structure: Sessions/, Plot Lines/, NPC's/, World (Erodas)/, Gods/, Factions/, History/, Species/, Things and Objects/
- Templates are in `z_Assests/Templates/`
- `z_Assests/Inspiration/` provides context of other stories that I the creator like. These are an incomplete list of things that I would like to keep track of just so AI may pull common themes out of these stories
- Upon startup please check the to do list and see if there is a new session with details to fill in additional info for notes — remove items from to do that seem complete
- Homepage.md is my hub where I interface with this database
- The z_Assets folder is for anything that has more to do with the backend of the vault/articles
- Consistency is key. If you make/see a note that doesn't follow vault conventions please flag it for us
- 

### What Gets Its Own Article
An article should exist if the subject is a **unique worldbuilding element** or **part of the story**:
- **People and places always get their own article** — every named NPC, PC, location, faction, and god
- **Things get an article when** unique to Erodas, relevant to a story or history, or of cultural/religious/narrative importance. Mundane real-world items (a hammer, a generic sword) do not need articles — but named unique items (*Sword of Ulthagos*) do.
- **Dates** do not get standalone articles unless historically significant — in that case, write a History (Event) article for what happened, not the date itself.
- **Article names must be unique.** Disambiguate with parentheses when needed: e.g. *Dithoria City* vs *Dithoria (God)*. Consolidate overlapping articles into one whenever possible rather than maintaining duplicates.

### Plot Lines vs History
- **Plot Lines** are *active history* — threads currently unfolding. They track what is happening now, what players know vs. don't, and what happens next if ignored.
- **History (Event) articles** are for concluded events. When a Plot Line resolves, merge its content into a History article and delete the Plot Line note.
- If a Plot Line and a History article cover the same subject, the History article takes precedence. Merge the narrative into it and remove the Plot Line.
- A useful plot engineering guide can be found: [[Plot Engineering Blueprint.pdf]]. Reference this when building new plots lines and histories.
- [[Plot Ideas]] are a very rough draft and stream of consciousness draft of the overall plot lines that I have planned for the world. There might be information that contradicts itself within this note, in instances that there are contradictions refer to the newer lines. 

## Note Types

Every note in the vault must have a `Type` property. The canonical types are listed below. When writing or editing any note, follow the rules for its type. If a note's type is missing or wrong, correct it.

All notes should follow the template for their type found in `z_Assests/Templates/`. When creating a new note, use the corresponding template as the starting structure. If no template exists for a type, flag it so one can be created.

---

### NPC
Non-player characters — enemies, allies, neutrals, shopkeepers, anyone the party can meet.
- **Required fields:** `Type`, `Status` (Alive / Dead / Unknown), `Affiliation`, `Location`
- **Optional:** `Plot_Lines` (list of Plot Line links this NPC is significant to — drives the Key NPCs query on each Plot Line note automatically)
- **Folder:** `NPC's/`
- **Content rules:** Lead with one vivid physical or behavioral detail. Every NPC must have a want — something they are actively pursuing. Include known history only; speculation goes in a callout. Link to every Faction and Location they are tied to.

### PC
Player characters.
- **Required fields:** `Type`, `Player`, `Status` (Active / Inactive / Deceased)
- **Folder:** `Player Characters/`
- **Content rules:** Written from a lore perspective, not a mechanical one. Include backstory, current goals, and key relationships. Update after sessions where something significant changes for the character.

### Location
Any named place — cities, towns, buildings, regions, dungeons, bodies of water.
- **Required fields:** `Type`, `Region`, `Status` (Active / Ruins / Unknown)
- **Optional:** `Faction`, `Notable_NPCs`, `MOC` (checkbox — mark true if this is a Map of Contents hub note)
- **Folder:** `World (Erodas)/`
- **Content rules:** Open with a strong sensory establishing detail. Describe what a visitor would notice first, then layer in history and factions. Link every NPC and Faction associated with it. If the party has visited, add a "In the Campaign" section noting what happened there.

### Faction
Any organization — guilds, governments, criminal syndicates, cults, military groups, crews.
- **Required fields:** `Type`, `Status` (Active / Disbanded / Unknown), `Base_of_Operations`
- **Optional:** `Leader`, `Allies`, `Enemies`
- **Folder:** `Factions/`
- **Content rules:** Describe goals, methods, and internal structure. Every faction should have at least one named NPC tied to it. Note the faction's relationship to the party explicitly if one exists. `Group` is a deprecated alias for this type — use `Faction` going forward.

### Species
Playable races, creature types, and notable populations.
- **Required fields:** `Type`, `Origin` (region or plane of origin)
- **Optional:** `Typical_Alignment`, `Subraces`
- **Folder:** `Species/`
- **Content rules:** Written as a naturalist or scholar would describe them — observations, not stat blocks. Include how they are perceived by other cultures in Korlornium. Avoid copying D&D sourcebook text; write it as native lore.

### God
Deities and divine entities worshipped or acknowledged in Erodas.
- **Required fields:** `Type`, `Domain`, `Status` (Active / Dead / Imprisoned / Unknown)
- **Optional:** `Worshippers`, `Holy_Site`, `Symbol`
- **Folder:** `Gods/`
- **Content rules:** Include myths, not just attributes. What do people believe this god did? What do their followers want? Gods should feel like characters with history and agenda, not just a list of domains.

### Event
Historical events — battles, disasters, political upheavals, divine acts.
- **Required fields:** `Type`, `fc-start` (in-world), `fc-end`, `Location`
- **Optional:** `Factions`, `Plot_Lines`
- **Folder:** `History/`
- **Content rules:** Written as if from a history book — past tense, authoritative tone. Note what caused it, what happened, and what changed as a result. Include at least one detail that makes it feel specific to this world rather than generic fantasy history.
- - `fc-type` refers to the type of event cultural holiday, historical, religious observance, or seasonal observance. This applies to all events

### Event
	Holiday
Recurring festivals, observances, and cultural celebrations.
- **Required fields:** `Type`, `Location` (where it is observed), `fc-start`, `fc-end` (fc start and end signify the start and end date of the event,
- fc-type = holiday and type =event
- **Folder:** `History/Calendar/`
- **Content rules:** Describe the observance from the perspective of someone living in the world — what do people actually do, hear, smell, eat? Include at least one regional variation. Tie it to at least one God, Faction, or historical Event if possible.
- `fc-type` refers to the type of event cultural holiday, historical, religious observance, or seasonal observance. This applies to all events

### Plot Line
Active or historical campaign narrative threads.
- **Required fields:** `Type`, `Status` (Active / Resolved / Dormant), `Locations`
- **Folder:** `Plot Lines/`
- **Content rules:** Written as a DM-facing document. Include what the players know vs what they don't. Track the current state of the thread and what will happen in the world if the party ignores it. Every active plot line should have a "next beat" — the next thing that happens if the party engages.
- **Key NPCs** are pulled automatically via Dataview from NPC and God notes that have this plot line listed in their `Plot_Lines` property — do not maintain a manual list.

### Session
Individual campaign session notes.
- **Required fields:** `Type`, `fc-start`, `fc-end`, `fc-category: Session`, `Location`, `Plot_Lines`
- **Optional:** `date` (real-world IRL date — **only filled in after the session has been played**)
- **Folder:** `Sessions/`
- **Content rules:** See Session & Scene Design Rules below. Scenes are planning notes written before the session.
- **Played vs. Planned:** A session is considered **played** if and only if its `date` field is populated. Sessions without a `date` are planned but not yet run.
- **Recap section:** The `# Recap` in a session note contains a summary of the **previous** session — written as a reminder at the top of the next session's note. It is *not* the recap of the session described in that file.

### Object
Mundane and magic items — weapons, armor, tools, curiosities.
- **Required fields:** `Type`, `Rarity` (Common / Uncommon / Rare / Very Rare / Legendary), `Owner`
- **Folder:** `Things and Objects/`
- **Content rules:** Include what it does, what it looks like, and where it came from. For magic items, describe the effect in plain language before any mechanics. Objects of significant narrative importance should have a history section.

### Artifact
Unique, legendary, or plot-significant items that transcend normal item rules.
- **Required fields:** `Type`, `Origin`, `Current_Location`
- **Folder:** `Things and Objects/`
- **Content rules:** Same as Object but always include a history and a sense of weight — why does this item matter to the world? Artifacts should feel dangerous or coveted. If it has a will or sentience, note it.

### Nature
Ecological entries — flora, fauna, natural phenomena, diseases.
- **Required fields:** `Type`, `Region`
- **Folder:** `Species/` (or `World (Erodas)/` if tied to a specific location)
- **Content rules:** Written as a field guide or bestiary entry. Include habitat, behavior, and cultural significance. How do the people of Korlornium use, fear, or name this thing?

### Vessel
Named ships, vehicles, or other significant conveyances.
- **Required fields:** `Type`, `Owner`
- **Folder:** `Things and Objects/`
- **Content rules:** Treat vessels like characters — give them personality through details. Include crew capacity, notable features, and history. Link to the NPC who commands it.

### Plane
Planes of existence, divine realms, and extraplanar locations.
- **Required fields:** `Type`, `Access` (how one travels there)
- **Folder:** `World (Erodas)/`
- **Content rules:** Describe the rules of the plane — how does it look, feel, and behave differently from the material world? Link to any Gods or Factions tied to it.

### Celestial Body
Moons, stars, constellations, and astronomical phenomena.
- **Required fields:** `Type`, `Cycle` (if applicable)
- **Folder:** `History/Calendar/`
- **Content rules:** Include both the physical description and the cultural meaning — what do people in Korlornium believe about this celestial body? Tie to Holidays or Gods where relevant.

### Culture
Cultural practices, traditions, languages, or customs that don't fit a single Faction or Location.
- **Required fields:** `Type`, `Region`
- **Folder:** `History/`
- **Content rules:** Written as an anthropological observation. Who practices this, when, and why? What does it reveal about the people of this region? `Customs/ Culture` is a deprecated alias — use `Culture` going forward.

### Date
Calendar entries — days of the week, months, and calendar system articles.
- **Required fields:** `Type`
- **Folder:** `History/Calendar/`
- **Content rules:** Describe the meaning and mythology of the day or month. What god or concept does it represent? How do people observe it?

### MOC
Map of Content — hub notes in `Bases/Index/` that embed a `.base` view and serve as navigational indexes for each note type. These are surfaced as a card gallery on the Homepage via `Hub.base`.
- **Required fields:** `Type`, `description`
- **Optional:** `cover` (image path shown on the card)
- **Folder:** `Bases/Index/`
- **Content rules:** Each MOC embeds exactly one `.base` file. Do not add prose. Formerly typed `BaseIndex` — use `MOC` going forward.

### Asset
Vault backend files — templates, indexes, settings, this file.
- **Required fields:** `Type`
- **Folder:** `z_Assests/`
- **Content rules:** No style rules — these are system files, not articles.
## General Advice
- I want the characters to feel like they have motive in the plots and characters should be able to shine in each session
- There needs to be consequences/trade offs to actions
- Mysteries should be presented three times for players to catch on subtle things happening around the world
- The world needs to feel alive and lived in any advice on making this feel more lived in is welcome, in the writing and when planning sessions.
- Use less folder structure and more properties
	- Folder will separate general types of articles but the properties should tell you specific categories and other property the thing/lore/etc. 
- Optimize whenever possible. Instead of manually writing or calling out things within certain categories, use functions and templates to call them.

## Session & Scene Design Rules
These rules apply whenever helping plan, write, or review sessions and scenes.

### Scenes
- Every scene must have at least two of: a **decision** (real tradeoff), a **revelation** (something changes or is learned), or **pressure** (stakes, time, cost). A scene with none of these should be cut or merged.
- Lead with one specific, vivid sensory detail rather than generic atmosphere. Make it specific to this world.
- NPCs in a scene must have a **specific want** — not a vague attitude. What do they need right now, and what will they do to get it?
- Name every scene descriptively (e.g. "The Ambush at Saltmire Docks") — never leave it as just "Scene."
- Scene types determine which callouts to use:
  - **Combat** — Summary, Note, Description, Combat, Item
  - **Social** — Summary, Note, Description, Challenge, Quote
  - **Exploration** — Summary, Note, Description, Challenge

### Sessions
- Open in the action — no travel montages or tavern waits at the start.
- Structure each session in three beats: establish the tension → complicate it → resolve it but open a new question. End on a hook.
- Alternate scene types across the session. Avoid back-to-back combat.
- Each player should have at least one spotlight moment per session — a scene that calls on their specific character.
- Plan **situations**, not plots. Define who wants what and why; let players drive the direction.
- If a plot thread is ignored, something happens in the world anyway. The world does not pause for the party.
- Consequences should be visible and proportional. Players need to feel that choices matter.

## During session
- I may ask quick questions during a session. Please take notes on this and I will integrate them into the current session's note immediately. Post-session we will discuss what needs to be added to the database outside the session notes.

## Commonly used Plug-ins including community plug-ins
- Bases (Core)
- Calendarium 
- Digital Garden - Would like to replace with github pages
- Dataview 
- TTRPG Tools: Maps
- Templater
- Homepage
- Buttons

## Resources for using Obsidian for TTRPGs
https://obsidianttrpgtutorials.com 
