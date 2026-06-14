---
dg-publish:
Type: Session
date: 2026-05-17
fc-start: 12004-02-35
fc-end: 12004-02-37
fc-category: Session
Location:
  - "[[The Seat of Thalmyre]]"
  - "[[Whelk's Landing]]"
  - "[[Coffin Rock]]"
Plot_Lines:
  - "[[Breaking the Chain]]"
  - "[[The Search for Tidemother Gate Stone]]"
  - "[[The Red Talons Fate]]"
---

# Recap
>  [[The Salty Bitches]] set sail from [[Stormveil]] across [[The Scar]] bound for [[Thalmyre]]. Mid-voyage, they were boarded by a crew associated with [[The Drifting Bastards]] who flung [[Kobold]]s onto [[The Salty Bitch]], nearly killing [[Picasso]] in the chaos. The crew repelled the attack. They earned the [[Thalmyre]] map from the encounter. Navigating the perilous waters surrounding [[Thalmyre]], they made port and were met by **Tumbo**, the dock warden — a man [[Vel'Korr]] nearly gutted before Tumbo defused the situation by blowing a raspberry on his belly. Tumbo pointed the crew toward a neutral bar called [[Whelk's Landing]], marked by a shell above the door.

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

# Scene: Opening — First Night in The Seat

> [!Summary]+
> The party steps off the docks into [[The Seat of Thalmyre]] on the first evening of [[Tidescrest]]. This is a pure orientation scene — let players absorb the chaos, describe what they want to investigate, and find their way to [[Whelk's Landing]]. No forced conflict. Set the world alive.

> [!Note]+
> Tidescrest runs **3 days**: tonight (eve, registration) + two full tournament days tomorrow and the day after.
> The Rattails are loudly celebrating their rise — fireworks and small explosions are going off in the streets. Keep it loud, sensory, kinetic.
>
> **Tidal anomaly (background detail):** The tide came in nearly two hours early this afternoon and went out again without warning — not dramatically, but wrong enough that dockworkers noticed. Fishermen have been complaining all week: nets coming up light, the usual current reversals not happening, and once a whole school of silverfish found floating, belly-up, for no reason anyone can name. Most pirates treat it as bad luck. Old hands are quiet about it. Don't make it a scene — let it surface through environment and NPC asides.

> [!Description]+
> The dock gate opens onto a street that hits you like a fist — noise, heat, and the sharp smell of gunpowder. Every building flies a banner: a driftwood anchor, a coiled snake, a foaming mug, a black wave. Lanterns string between rooftops and sway in the sea breeze. Somewhere close, something *explodes*, and the crowd cheers.
>
> A fire-breather balanced on a barrel sends a column of flame into the dark sky. A Kobold sprints past wearing two boots on his head and none on his feet. A gambling table overflows onto the cobblestones, five different species crowded around it arguing in four languages.
>
> On the dock side of the street, the waterline is wrong. Tide markers — painted rings on the pilings — show where the water should sit tonight. It's a foot and a half below the lowest ring. A grey-bearded sailor nearby is staring at it with his arms folded, not saying anything.
>
> Down the main drag, a hand-painted sign on a post reads: *TIDESCREST REGISTRATION — WHELK'S LANDING — TONIGHT ONLY.*

---

# Scene: Whelk's Landing — The Eve

> [!Summary]+
> The crew descends into [[Whelk's Landing]] for the first time. This is the social hub of the session — meet [[Darla Murdinthe]], take in the faction dynamics, register for the tournament, and receive the first whisper about a crew from [[Dithoria City]].
> The Drifting Bastards are seated in the far corner. The party can confront them or leave it alone — their choice.

> [!Note]+
> **Faction tables tonight:**
> - **[[The Rattails]]** — loud, drunk, celebrating. [[Tompkins 'The Squealer' Longtooth]] is standing on his chair at some point. Firework goes off inside briefly.
> - **[[Murky Bellows]]** — three quiet figures in the back booth. Watching everyone. Say very little.
> - **[[The Drifting Bastards]]** — six Goblins and one very large Kobold in the corner. One of them is wearing a boot around his neck. They glance at the party but don't make a move. Party can choose to interact.
> - **[[The Blackwake Company]]** — two well-dressed humans and a half-elf, clearly uncomfortable with the atmosphere. Nursing wine. Discussing something in low voices.
>
> **Tournament registration:** Darla keeps a ledger behind the bar. She charges **5gp per event per person** as an entry fee. She writes names in ink that seems to glow faintly. Each event is sponsored — winner gets a private sit-down with the sponsoring gang's representative.
>
> **Darla** won't be pushed around, bribed, or charmed into bending rules. She *is* the neutral ground. Anyone who starts a fight inside gets barred for life — and in Thalmyre, that means something.
>
> **Kel spotlight:** Darla is serving a grain porridge alongside the ale — she trades with a supplier out of [[Duskwind Landing]] and has carried the recipe for years. If Kel tastes it or asks about it, he recognises it immediately. It's his parents'. The [[Side Quest Tavern]]'s porridge, sitting on a bar at the edge of the world. Darla doesn't know whose recipe it is. She just likes it. His parents' work outlived their tavern.

> [!Description]+
> The shell above the door is bigger than it looked from the street — a full whelk the size of a wagon wheel, pale and salt-scarred, mounted like a trophy. Below it, a wooden staircase drops steeply into the earth. The torches thin out as you descend, until the only light is a pale blue-green glow from below.
>
> Then the room opens up and it stops you cold. The walls are *glass* — thick, old, slightly warped — and on the other side is the sea. Actual ocean floor, ten feet below the waterline. It should be alive with crabs and slow-moving bottom-feeders. Tonight the sand is bare. No crabs, no worms, nothing picking between the stones. One fish drifts past, upside down, slow, fins trailing. The bioluminescent fronds that usually light the far wall are dark. Figurines and statues line every shelf — icons from a dozen cultures, symbols of old gods, bone carvings, things with no clear origin.
>
> The pirates inside look like they broke in. Mangy, loud, scarred, dripping saltwater onto polished stone floors. A Sea-folk woman behind the bar watches all of it with the calm of someone who has seen considerably worse.

> [!Challenge]+
> **If the party confronts the Drifting Bastards:** The big Kobold, **Crunch**, stands up slowly. He's wearing a boot around his neck on a cord. He says nothing for a moment. Then: *"Nice boots."* — DC 14 Intimidation or Persuasion to defuse without a scene. Success: Crunch sits back down and says they're square. Fail: He calls over two friends and Darla has to intervene. Either way, no fight in Whelk's Landing.
> **If they ignore the Drifting Bastards:** The Kobold watches them register. Notes are being taken. This will matter later.

> [!Quote]+
> **Darla**, setting down two cups without being asked:
> *"Sparklefish gumbo's off. Whelk's good. Ale's better. You're registering, you pay tonight, you show up tomorrow, you don't bleed on my floor. Anything else?"*

---

# Scene: The Dithoria City Crew

> [!Summary]+
> A drunk [[The Rattails|Ratails]] pirate starts talking loudly about a crew that arrived this afternoon from [[Dithoria City]]. Fancy wizard. Lots of dead men walking around. The crowd finds it hilarious — city folk never survive the first round. 
> This is [[Vel'Korr]]'s spotlight. He knows before anyone says the name.

> [!Note]+
> Don't confirm it's [[Viros]] through NPC dialogue — let the description do it. The party should piece it together.
> The Dithoria crew has registered for **The Brawl** and **The Sailing Race**.
> **[[Picasso]] spotlight — auto-fail Wisdom save, no roll:** As this conversation happens, [[Sliver]] crawls out of Picasso's pocket, sniffs once toward the glass wall, and bolts under the table. He does not come back out.
>
> 

> Picasso looks at the glass. The bioluminescence on the far wall has gone dark in one section. The sand is bare. And then, at the very edge of the black water, something enormous and white drifts into view — slow, deliberate — and it turns one vast pale eye directly at him.
>
> **The bar disappears.**
>
> He is in open water. Cold, absolute pressure, no sound except a low hum he feels in his sternum. [[Cthulhu]] is in front of him — massive, luminous, tentacles spread wide in what is unmistakably a greeting. It is *thrilled*. It drifts toward him with the energy of something that has been waiting.
>
> It doesn't speak. It shows him things — impressions, not images. A great chain, slack and crumbling. A light far below the ocean floor, guttering like a candle about to go out. Something immense and ancient at the center of it, dimming. The [[Tidemother]]. Dying.
>
> Then Cthulhu turns that eye back on Picasso. The tentacles spread wider. The hum in his chest becomes a full-body pressure. The contact shifts — less vision, more *voice*. Warm. Almost offended.
>
> *There you are. I've been trying to reach you. Do you know how long it's been?*
>
> It is delighted to see him. Genuinely. It has the energy of something that has been waiting by the door.
>
> *We are standing at the nexus, you and I. The balance on [[Erodas]] is about to shift and you are exactly where I need you to be. The Tidemother —* a flicker of distaste, deep and certain *— she has ruled these waters with too much compassion. She is failing. She will be eliminated. Something must fill that space.*
>
> A pause. Then, with the cheerful certainty of someone presenting a very good idea:
>
> *There is a powerful being in pain. You will find it. Cut out the rot. Plant this where the rot was. Then I can come through.*
>
> Something appears in Picasso's closed fist. Small. Dense. Warm in a way that has nothing to do with temperature. A seed — dark, faintly luminescent, smooth as a river stone. It does not feel like something that should exist outside of very deep water.
>
> *Don't lose it. I've missed you.*
>
> **Back in the bar.** Dry. In his seat. The conversation around him hasn't stopped. Nobody noticed. [[Darla Murdinthe]] is staring at the dark section of glass behind Picasso's head. When he turns, there's nothing there. She looks at him — just for a moment, Sea-folk eyes flat and unreadable — then goes back to drying the cup.
>
> [[Sliver]] stays under the table for the rest of the night.
>
> **What Picasso knows:** The Tidemother is dying and Cthulhu wants her gone. There is a powerful being in pain somewhere ahead of them. The seed is the choice — plant it and Cthulhu comes through, don't plant it and the being dies. He doesn't know yet what the being is. He will know it when he sees it.
>
> **DM note:** Don't prompt Duncan to share this or use the seed. The choice lands at [[Coffin Rock]]. Let him carry it there himself.

> [!Description]+
> A Rattails pirate two tables over slaps the table and laughs so hard he spills his ale:
> *"— and they walk in all serious, right, the wizard's got this long coat, real fancy, and his crew — I swear on Tidemother's teeth — his crew are DEAD. Like, walking, but wrong. Arms hanging. Eyes forward. Six of them. Seven maybe."*
> His friend: *"They register?"*
> *"Oh yeah. Brawl and the race. Going to be the best Tidescrest in years."*

> [!Quote]+
> If Vel'Korr approaches and asks for a description of the wizard:
> *"Elf. Real pale, even for an elf. Long coat, dark red — or maybe it's just the blood. Has a rod of some kind on his belt, looked like it had — I dunno — fingers? Walked in like he owned the place. You know him?"*

---

# Scene: Tidescrest — The Rum Chug

> [!Summary]+
> The party has time to breathe before things go wrong. Let them enjoy Tidescrest — enter the Rum Chug, wander the street events, spend money at [[The Blowpipe]], get thrown out of [[The Black Bar]]. This is the last easy moment of the session.

> [!Note]+
> Keep this loose. Let players drive. The street events below are tools — drop whichever ones the party walks into, ignore the rest.
> The Rum Chug is the one structured event. Run it if the players want to compete; skip it if they're having more fun elsewhere.

---

## Rum Chug *(Murky Bellows)*

> [!Description]+
> [[Darla Murdinthe]] lines up eight clay mugs on the bar. The crowd presses in three deep. No rules are posted. You'll understand when it starts.
> The mugs are filled with [[Agithian Ale]] — except the last round, where something green and faintly luminescent has been added.

> [!Note]+
> Up to **3 contestants** compete simultaneously. Track separately per PC.
> NPCs at the bar will bet loudly — if someone fails publicly, lean into the crowd reaction.

> [!Challenge]+
> **Three rounds. Each round: Constitution saving throw.**
> | Round | DC | Contents |
> |---|---|---|
> | 1 | 11 | Agithian Ale |
> | 2 | 13 | Agithian Ale, double-poured |
> | 3 | 15 | The mystery cup — green, smells like the ocean floor |
>
> - **3 saves:** Win. [[Murky Bellows]] rep buys a round and wants to talk later.
> - **2 saves:** Solid showing. Crowd cheers, you're known.
> - **1 save:** You're the entertainment. Crowd boos affectionately.
> - **0 saves:** You wake up on the bar. Darla looks disappointed.
> **Wild card:** Fail the Round 3 save → **DC 14 Wis save** or spend the next hour hallucinating. Something in the green cup. The Murky Bellows rep watches to see who finishes it.

---

# Scene: Tidescrest — The Streets

> [!Summary]+
> The party moves through the festival streets of [[The Seat of Thalmyre]]. Use any of the events below as flavour or let players engage with them. These are not encounters — they are texture. Drop them naturally as the party moves around.

> [!Note]+
> Mix and match. Not all five need to happen. Read the room — if players are engaging, let it breathe. If they're itching to move, give them one moment and keep walking.
>
> **The Dithoria tattoo artist:** The man at the far end of Tattoo Alley whose line is inexplicably the longest. He's wiry, cheerful, from [[Dithoria City]]. He sells two designs: one he claims means *"warrior of the sea"* in Draconic, one he claims means *"eat my ass."* Crowds love the second one. Both are the same rune. Both are [[Viros]]'s possession mark.
> If any player gets one, note who quietly and hand them a slip of paper when the Seizure scene triggers. The slip reads: *"A pull, low and certain, like a tide you didn't know was moving. Coffin Rock. You don't know why you know the name. You know it anyway."*
> The player decides what to do with this. Do not prompt them. Do not follow up.

> [!Description]+
> Every street is loud and smells of gunpowder and fried fish. Lanterns swing between rooftops. Somewhere close, something explodes and the crowd cheers.

**The Greased Mast** — A ship's mast planted in the square, greased head to toe, prize tied at the top. Three species are currently stuck halfway up. A [[Goblin]] bookmaker takes bets on who slides down first.

**The Rattail Firework Duel** — Two [[The Rattails|Rattail]] pirates firing handheld fireworks at each other across the street. Neither will flinch. The crowd is three deep and screaming. The fireworks are labelled *"NOT FOR INDOOR USE."* One of them is indoors.

**The Prophecy Cart** — A [[Tiefling]] in a dramatic cloak selling *"Official Tidescrest Prophecies — 5gp each, guaranteed accurate."* Every slip reads the same: *"You will find what you seek, but not where you look."* He has sold forty of them. He has no regrets.

**The Singing Shark** — A [[Gnome]] pressing a tiny instrument against a tank containing a very unhappy shark, insisting to a growing crowd that it is singing. It is not singing. The crowd is divided.

**Tattoo Alley** — A row of artists doing Tidescrest commemorative tattoos. At the far end, a wiry man from [[Dithoria City]] is doing a roaring trade — his line is the longest on the street. He's got the funny one, he says. Ask him about the Draconic tramp stamp.

---

# Scene: The Dead Man's Trail

> [!Summary]+
> A Tidescrest tradition running twenty-odd years: **Manka** encodes Torlan's last route across the Seat on a set of tile clues, hides something at each stop, and lets whoever can follow it claim the haul. This year the tides have moved things. The trail ends somewhere it has never ended before.

> [!Note]+
> **The tradition:** Entry is free. Manka hands over the first tile at a carved boot post near the fish market. Each tile has a scratched riddle pointing to the next location. At each stop, something is hidden. Party works together — anyone can attempt a check, others can Help.
> **Manka:** Stout, weathered, one boot hanging from her belt by a hook — she doesn't explain it. Warm and rambling about the trail's history, genuinely unsettled about the tide. She's been doing this long enough to know when something is wrong. She knows right now.
> **Tidal note:** The tide is sitting a foot and a half below where it should be. A flat basalt shelf on the eastern edge — always submerged — is exposed for the first time Manka can remember. She waded out to check it this morning. Something was already there. She left it. She doesn't know what to make of that.
> **Prize pool:** [[Deadman's Coin]], [[The Carapace]], [[The Unshackle]], Healing Potion ×2 — one per stop. Whatever they find, they keep. The Deadman's Coin is always on the shelf.
>
> **The four stops:**
> | Stop | Riddle | Skill | DC | Location |
> |---|---|---|---|---|
> | 1 | *"Where the catch is counted and the day begins, look below the number that was never used."* | Investigation | 12 | Fish market — scratch under a barrel stave |
> | 2 | *"Ask the man who breathes fire where the smoke goes when the wind changes."* | Persuasion or Perception | 13 | Fire-breather's barrel — tile tucked in a boot he leaves as a prop |
> | 3 | *"The oldest post in the Seat has a ring at the right height for a man who is no longer the right height."* | History or Investigation | 13 | Old harbourmaster's post — tile wedged at the six-foot mark |
> | 4 | *"The tide knows where Torlan is. Ask it."* | — | — | Eastern shelf — exposed basalt, something already there |
>
> **Fail a check:** One retry at disadvantage. Fail again: that item is missed, Manka gives a gentle redirect and they move on.
> **Stop 4 (the shelf):** No check required — the Deadman's Coin is sitting in a crack in the rock. But describe the tide moving wrong as they reach it. It comes back in faster than it should. The shelf is dry for seconds longer than it has any right to be, then the water rushes back. Manka watches from the shore and says nothing until they return.

> [!Description]+
> The carved boot has been on that post so long the wood around the nail has grown to hold it. Someone has painted it red again this year — fresh, a little uneven. A cluster of kids and two grown pirates trying very hard to look casual are gathered around it.
> Manka stands to one side, arms folded. She's maybe sixty, sun-cracked, one boot on her foot and one hanging from her belt on a hook. She doesn't introduce herself.
> *"Torlan walked this route the day he died and buried everything he had. You follow the tiles, you find the haul."*
> She holds out the first tile.
> *"There's a fourth stop this year. Out on the shelf. I didn't put it there."*

> [!Challenge]+
> **4-stop skill challenge.** Party works together — any player rolls, others Help for advantage.
> **Each successful stop:** Item found and claimed.
> **Stop 4:** Always reachable — Deadman's Coin always found. Describe the tide wrong.
> **Tidal moment:** When they return with the Coin, Manka is still watching the waterline.
> *"That rock has been underwater every Tidescrest I've run this trail."*
> She doesn't say anything else.

---

# Scene: The Greased Mast

> [!Summary]+
> The mast in the centre of the festival square — sixty feet, greased from base to top, prize tied at the peak — is the Tidescrest's most reliable spectacle. **Gorvin** has won it four consecutive years. He is enormous, soft-spoken, and completely serious. The crowd is not.

> [!Note]+
> **The event:** One climber from the party. The rest assist from the ground. Race against Gorvin. First to the top wins.
> **Gorvin:** Half-giant. Moves with the careful deliberateness of someone who learned young that things break around him. He climbs with the methodical patience of a man who has never fallen. Shakes every hand after — win or lose — with both of his. Has never visibly celebrated. Has also never lost. He is not cruel about this.
> **Assisting:** Party members on the ground can use the Help action to grant advantage on one Athletics or Acrobatics check per round — shouting timing, bracing the base, general encouragement the climber pretends not to need.
> **Gorvin's climb:** He rolls Athletics +8 each round with no assistance. He does not hurry. He does not fall. If the party's climber beats all three DCs before Gorvin completes three successful rolls, they win.
> **The locked box:** A small iron box on a folding stool at the base of the mast. Gorvin carries it to every Tidescrest. If asked what's inside: *"Something useful. I find that discourages losing on purpose."* Opens only for a winner.
> **Prize pool:** [[Saltfire Flask]], [[The Crackbone]], Healing Potion ×1.
> **Tidal note:** A dark waterline stain runs along the base of the square cobblestones — six inches higher than it should be, from a surge that came through wrong two days ago. Gorvin has moved the box away from it. He noticed. He hasn't said anything.

> [!Description]+
> The mast rises from the centre of the square — a full ship's mast, sixty feet, gleaming with grease from base to tip. A prize package is lashed to the top. Three different species are currently at various points on it, slowly sliding back down. The crowd is screaming.
> Gorvin stands at the base with his arms folded. He nods once.
> *"One climber. The rest can shout."*
> A Goblin bookmaker nearby is already taking bets. The odds on Gorvin are not good for the party.

> [!Challenge]+
> **3 Athletics or Acrobatics checks to reach the top.**
> | Section | DC | Notes |
> |---|---|---|
> | Lower third | 12 | Fully greased. Just grip and hope. |
> | Middle third | 14 | Less grease — but arms are burning. |
> | Top third | 16 | Almost bare — but sixty feet up with nothing below you. |
>
> Ground party members may Help once per round (advantage on one check).
> Gorvin makes Athletics +8 rolls each round with no help. He needs 3 successes to reach the top.
> **Win:** Climber reaches the top first. Gorvin opens the box.
> **Tie:** Gorvin opens the box anyway. *"Good climb."* He means it as a compliment. It is the highest compliment he gives.
> **Loss:** He descends. Shakes every hand with both of his. The box goes under his arm. The Goblin bookmaker makes a lot of money.

> [!Quote]+
> *(if they ask how he wins every year)*
> *"I don't slip."*
> *(if someone falls)*
> He watches them land. *"Are you injured?"* — He means it. He will wait before climbing.

---

**The Glass Sword** — A [[Tiefling]] at the south end of the festival grounds, horns sweeping back from his brow in a slow curl — the shape of a ram's. He juggles first: knives, a torch, a live crab he seems to have borrowed from somewhere. Then he kneels and draws a pinch of sand from a pouch at his hip. He breathes on it. Six translucent swords rise from his palm and begin to move — slow arcs, catching the torchlight like they're thinking about it. The crowd goes silent. Then they lose their minds. He travels with the other acts. No fixed home, new city every season. **[[Kel]] spotlight** — the horns curl like a ram's. He'll see it before anything else registers. This man moves through the world the way [[Forgas]] intended: craft, motion, no anchor. Don't prompt Kel. Watch what he does.

**The Menagerie** — A large canvas tent at the end of the main drag, billed as *"Tidescrest's Most Unusual Beasts."* Inside: a two-headed eel in a tank, something enormous under a velvet cloth that breathes visibly, a cage of creatures that look like they were designed by someone who had only heard birds described. **[[Sofaylie]] spotlight** — the Wok-woks react the moment she enters. Not scared. The opposite. They press against her, alert and bright-eyed, communicating something she can almost read. One of the caged creatures reaches a limb toward them through the bars. The handler looks nervous. The Wok-woks look like they've found something they recognise.

---

# Scene: The Captains' Brawl — Tidescrest Main Event

> [!Summary]+
> The main event of Tidescrest: an open brawl between the captains and lieutenants of the competing gangs. [[Captain Bubblebeard]] is competing — and clearly enjoying himself. The party can enter, watch, or bet. After the event, they can approach him.
> He's warm, distracted, ale in hand. He promises to sit down with them in the morning.
> **[[Vel'Korr]] and [[Faefi]] spotlight — the man they've been hunting is twenty feet away and currently headbutting a half-orc.**

> [!Note]+
> Bubblebeard fights like a force of nature — part warlock hex, part werewolf fury. His glass eye doesn't slow him down. Keep him *likeable*. He's loud, laughing, pulling people off the floor after he knocks them down. He's not cruel. He's having a wonderful time.
>
> **If the party enters:** One roll per player, punchy and fast. This is spectacle.
> | Action | Check |
> |---|---|
> | Land a solid hit | DC 14 Athletics or Attack vs AC 12 |
> | Stay standing after taking one | DC 13 Constitution |
> | Do something the crowd loses their mind over | DC 13 Performance |
>
> **After the brawl — what Bubblebeard tells them:** He doesn't have the Gate Stone. He's had too many strange eyes on him this week to keep it close. He hid it days ago somewhere safe, and he'll take them there himself after his match tomorrow. He won't say where — not in a packed festival port, not tonight. If they press: *"The less who know, the longer it stays where it is. Tomorrow."*
>
> He means it. He's being careful. He's just out of time.
>
> **The seizure happens during this scene.** See next scene.

> [!Description]+
> The fighting pit is a ring of barrels on the main dock — torchlit, roped off with ship's cord, packed four deep. Six captains have entered. The crowd is screaming.
>
> [[Captain Bubblebeard]] is already in the ring. He is enormous. The mist drifting from his broken horn catches the torchlight. His glass eye catches nothing. He is grinning wider than seems reasonable for a face that size.

> [!Quote]+
> *(after the brawl, pulling someone up by the collar)*
> *"Good fight. Buy me a drink and I'll remember your name."*
>
> *(if they tell him about Viros)*
> *"Aye. I've heard that name too many times this week. Come find me tomorrow morning — Itchy Finger, ask for the door with the red fish. We'll talk properly then."*

---

# Scene: The Wrong Moment

> [!Summary]+
> Mid-brawl, a woman in the crowd stops. She just stops. Her ale tips in her hand and doesn't spill. Her head turns toward the water. Then she sets the cup down carefully and walks away through the crowd with complete, unhurried purpose. Nobody else notices.
> **If any player got a tattoo from the Dithoria artist, hand them their slip now.**

> [!Note]+
> Don't announce this. Don't point at it. Describe it quietly and keep going. If a player calls it out, the crowd brushes it off — she probably had too much to drink.
>
> **If players follow the woman:** She doesn't acknowledge them. She walks to the dock's edge, looks at the water, and stops there. If they touch her, she turns her head slowly. Her eyes are focused on something past them. She says: *"Coffin Rock."* Then she goes quiet again.
>
> **If players examine her:** DC 13 Perception or Medicine — she has a fresh tattoo on her lower back. Runic. [[Vel'Korr]] needs no roll: he has seen these exact symbols carved into the bodies in [[Viros]]'s tower.

> [!Description]+
> She's maybe forty, sun-scarred, Rattails patch on her jacket. She sets her cup down like she's setting it down for the last time. Then she is gone into the crowd, moving against the flow.
>
> The fight in the ring goes on. Nobody notices but you.

---
---
# ⚓ PART TWO — THE MORNING AFTER
---


# Scene: Bubblebeard Is Dead

> [!Summary]+
> The party wakes to wrong-quiet. Not festival-quiet — wrong. Bodies in the streets. Half the stalls abandoned mid-setup. [[Captain Bubblebeard]] was found dead in his room an hour ago. How the party arrives here depends on where they slept.

> [!Note]+
> **If they slept on the ship:**
> They row in to a changed port. The noise is gone. From the water they can already see bodies slumped at stalls, lanterns still burning over nothing. Nobody on the docks. They find out about Bubblebeard when they reach [[Whelk's Landing]].
>
> **If they slept on land:**
> Sometime in the night — roll a DC 13 Perception for whoever is on watch, or just trigger it quietly. A figure is in the room. Still. Waiting. One of the controlled festival-goers, a knife in hand, positioned near the bed of whoever seemed most threatening. No dramatics — just a quiet, wrong presence in the dark. If they deal with it: the figure has the tattoo. After that the night is undisturbed. In the morning, they wake to silence.
>
> **The body:** No visible wounds on Bubblebeard. He looks like he sat down and stopped. His glass eye has been removed and is missing. His boots have dark basalt dust ground into the heel — he'd been to the hiding spot recently.
>
> **[[Darla Murdinthe]]** is behind the bar, expression flat. She found him. She won't say much. If the party pushes: *"Take what you need and go fix it. Whatever it is."*
>
> The Stray Dogs are split: those who are genuinely grieving and angry, and those who are walking toward the eastern docks without responding when called. The compromised ones don't react to their names.

> [!Description]+
> **From the ship:** The port is wrong before you dock. Lanterns burning over empty stalls. A body face-down on the cobblestones near the fish market. No sound except gulls and the water.
>
> **From land:** You wake and the festival is gone. Not ended — stopped. Mid-sentence. A half-eaten plate on a table outside. An untied banner snapping in the wind over nobody.
>
> [[Darla Murdinthe]] meets you at the bottom of the stairs. She doesn't say good morning.
> *"He's upstairs. You should see him before the Dogs do something stupid."*

---

# Scene: Tracing the Runes

> [!Summary]+
> The party pieces together what happened. The tattoo artist's stall is abandoned. The people walking toward the water all have the same fresh rune. The symbols match what [[Vel'Korr]] saw carved into the bodies in [[Viros]]'s tower. They point to [[Coffin Rock]].

> [!Note]+
> **Clues:**
> - The Dithoria artist's stall: packed up cleanly overnight. No sign of struggle. Gone.
> - Two bodies in the alley behind Tattoo Alley — they didn't survive activation
> - Every compromised person walking toward the docks has the same fresh rune on their lower back
> - DC 14 Arcana: it's a command glyph — activation-based, requires a central anchor still running
> - DC 12 Investigation near the docks: all tracks lead to a rowboat launch point, direction [[Coffin Rock]]
> - **[[Vel'Korr]]:** no roll needed — he knows these symbols. He saw them on the bodies in the tower. He just didn't know what they were for.
>
> **If a player is compromised:** They know where to go without any of this. They knew when they woke up.

> [!Challenge]+
> **Move fast:** They can reach [[Coffin Rock]] before the ritual completes. Viros doesn't have full control yet.
> **Delay:** The ritual completes. The Gate Stone moves. Harder to stop.

---

# Scene: Coffin Rock

> [!Summary]+
> [[Coffin Rock]] is a narrow basalt island half a mile off [[Thalmyre]]'s eastern shore. The controlled townsfolk stand in silence around a large excavation cut into the top of the rock — they have been digging for days. The chamber below is where [[Viros]] is completing his ritual with the [[Tidemother]] Gate Stone.
> [[Mother Elyra]] is down there. The [[The Red Talons|Red Talons]] are down there. So are [[Zora Meadowlark]] and [[Sibil Meadowlark]] — and they are mid-argument with Viros when the party arrives.
> This is the final encounter. **[[Vel'Korr]], [[Faefi]], [[Picasso]], and [[Kel]] spotlights.**

> [!Note]+
> **Exterior:** Sixty, seventy controlled people ring the excavation in silence. They don't move unless the party tries to pass. They are not combatants — they are witnesses. If the party pushes through, they part. They are not here to fight. They are here because they were told to watch.
>
> **Descending:** Iron rungs hammered into the rock wall. The chamber opens below — torchlit, salt-damp, the sound of water moving somewhere beneath the floor. It smells wrong. Like something very old that has been exposed to air for the first time.
>
> **[[Mother Elyra]]** stands at the chamber entrance, facing out. She doesn't look at [[Faefi]] until Faefi calls her name. Then she turns — and she smiles exactly right. **[[Faefi]] spotlight.**
>
> **[[Vel'Korr]]:** The Red Talons stand arranged behind [[Viros]] in the chamber. All of them — Varnak, Astra, Joanos, and three unnamed crew — reanimated, in red coats, eyes forward. He sees [[Astra]] first. **Give him a moment before anything else happens.**
>
> **Varnak:** When Vel'Korr approaches and speaks to him — uses his name, invokes [[Beak]], invokes their history — DC 16 Charisma (Persuasion), one attempt. Success: Varnak turns and fights for them. When Viros dies, the control breaks and Varnak gets a real moment before he goes. Failure: Vel'Korr has to put him down himself.
>
> **Elyra's end:** When Viros dies, Elyra collapses. For just a breath she is herself — eyes clear, present, free. She looks at Faefi. She's happy. Then she is gone.
>
> **[[Picasso]] spotlight:** The seed is in his pocket. The "powerful being in pain" is the guardian dragon, void-corrupted, emerging from the Gate Stone's destruction. He will recognise it when he sees it. Don't prompt him. Watch what he does.
>
> **If a player is compromised:** They feel the pull to walk to Viros's side the moment they enter the chamber. Give them the moment. Watch what they do.
>
> **[[Zora Meadowlark]] and [[Sibil Meadowlark]]** are already in the chamber when the party descends. They came for the Gate Stone — it was part of a deal. Viros is not honoring the deal.
>
> **The argument (already in progress when the party arrives):**
> Viros wants to use [[Thorne]]'s body — absent, and therefore vulnerable — to retrieve the [[Parsus]] Gate Stone. He needs a vessel with a connection to that domain and [[Thorne]] is the closest candidate. He is presenting this to Zora as a logical next step. Zora finds it a breach of their arrangement. [[Sibil]] is standing slightly apart with her hand on her weapon, watching, not intervening yet.
>
> **What Zora's objection actually is:** Not morality. Unpredictability. Viros is improvising, and improvising people make mistakes, and mistakes introduce variables. She agreed to a specific arrangement. He is changing it. That is not acceptable.
>
> **Flipping Zora — DC 14 Charisma (Persuasion):** The party can interrupt the argument and make their case. What works: Viros will use her the same way he uses everyone else. She is already a variable in his plan — she just hasn't realised it yet. She is not a partner; she is a tool he hasn't deployed yet. What doesn't work: appeals to heroism, mercy, or the greater good. She doesn't care.
> - **Success:** Zora holds Viros's gaze for a long moment. Then she turns to [[Sibil]] and says one word: *"Now."* Sibil grins. Combat begins with both as allies.
> - **Failure or no attempt:** Zora doesn't flip immediately — but Viros will do something in the first round that tips her anyway (dismisses her, uses her as a shield, or simply turns his back on her to address the party). She turns by round 2 regardless. The difference is whether the party earned it.
>
> Viros does not attack immediately. He lets them see. He is, genuinely, not worried.

> [!Description]+
> The rock rises twenty feet out of black water. No dock, no steps — iron handholds hammered into the basalt in a line. The people at the top don't move as you climb. They watch. Sixty of them, maybe more, standing at the lip of a massive hole cut into the centre of the rock.
>
> The excavation drops thirty feet into the earth. Below: torchlight. The smell of salt and something older than salt.
>
> You go down.
>
> The chamber is rough-hewn and wide, ceiling low, water seeping between the stones. At the far end, [[Viros]] stands over the [[Tidemother]] Gate Stone — cracked, pulsing with a dark light that doesn't illuminate anything. Behind him, standing at attention: six figures in red coats. You know these faces.
>
> Closer to the base of the rungs, two women face him. One is still, hands folded, speaking in a measured voice. The other has her hand on her weapon and is smiling like she's already decided how this ends. Neither of them has noticed you yet.

> [!Quote]+
> **The argument (before the party is noticed):**
> **Zora:** *"This wasn't the arrangement."*
> **Viros:** *"The arrangement evolved. Kill the girl and we move forward."*
> **Zora:** *"You're introducing variables. I don't work with variables."*
> **Viros:** *"You work with* me. *Kill her."*
>
> **When Viros notices the party — he doesn't look up from the ritual:**
> *"I wondered when you'd show up."*
> *(a slight gesture toward Elyra at the entrance)*
> *"She's here, by the way. She never does work quite right the first time."*
>
> **If the party addresses Zora directly:**
> *"He'll use you the same way."*
> — She already knows. She's deciding whether she cares.

> [!Combat]+
> ## PHASE 1 — Viros + The Red Talons
>
> **Setup:** Party descends into an argument already in progress. Zora and Sibil are facing Viros. Elyra is at the entrance. Red Talons arrayed behind Viros. The party can interrupt, watch, or act. Combat begins when the party attacks, when Zora flips, or when Viros decides everyone has had long enough.
>
> **Zora and Sibil's starting position:** Neutral until flipped. If the party persuaded Zora (DC 14), they are allies from round 1. If not, Viros does something in round 1 that tips Zora anyway — she turns at the start of round 2 regardless. Sibil follows Zora's lead, immediately and happily.
>
> ---
>
> ### VIROS *(Modified Mummy Lord — CR 15)*
> | | |
> |---|---|
> | **AC** | 16 (natural armour) |
> | **HP** | 100 *(reduced from MM — cross-check and adjust)* |
> | **Speed** | 20 ft |
> | **Legendary Resistances** | 2/day *(reduced from 3)* |
>
> | STR | DEX | CON | INT | WIS | CHA |
> |---|---|---|---|---|---|
> | 18 (+4) | 10 (+0) | 18 (+4) | 11 (+0) | 18 (+4) | 16 (+3) |
>
> **Saving throws:** CON +9, WIS +9, CHA +8
> **Damage immunities:** necrotic, poison
> **Condition immunities:** charmed, exhaustion, frightened, paralyzed, poisoned
> **Magic Resistance:** advantage on saves vs. spells and magical effects
>
> **Multiattack:** Dreadful Glare + 2 Rotting Fist attacks
>
> **Rotting Fist** *+9, reach 5 ft* — 2d6+4 bludgeoning + 2d6 necrotic. Target makes DC 16 Con save or is **Cursed** — their max HP is reduced by the necrotic damage taken. Lasts until *Remove Curse*.
>
> **Dreadful Glare** *60 ft* — DC 16 Wis save or **Frightened** until end of next turn. Fail by 5+: also **Paralyzed**.
>
> **Legendary Actions (3):**
> - *Rotting Fist (1)* — one Rotting Fist attack
> - *Channel Negative Energy (2)* — 60 ft radius, DC 16 Con save or take 2d6 necrotic and can't regain HP until end of next turn
> - *Blasphemous Word (2)* — one creature within 10 ft, DC 16 Con save or **Stunned** until end of its next turn
>
> ---
>
> ### RED TALON MUMMIES *(Standard Mummy — CR 3, ×5)*
> *Varnak, Astra, Joanos + 2 unnamed crew. All in red coats.*
>
> | **AC** | 11 | **HP** | 40 each *(reduced)* |
> |---|---|---|---|
> | **Speed** | 20 ft | **Fire** | Vulnerable |
>
> **Damage immunities:** necrotic, poison
> **Condition immunities:** charmed, exhaustion, frightened, paralyzed, poisoned
>
> **Rotting Fist** *+5, reach 5 ft* — 2d6+3 bludgeoning + 2d6 necrotic. DC 12 Con save or Cursed (max HP reduced).
> **Dreadful Glare** *60 ft* — DC 11 Wis save or Frightened until end of next turn.
>
> **VARNAK specifically:** HP 58 (full). When [[Vel'Korr]] speaks to him and succeeds DC 16 Persuasion — Varnak turns. Fights for the party. Uses Rotting Fist against Viros. When Viros dies: control breaks, Varnak gets his moment.
>
> ---
>
> ## PHASE 2 — The Void Guardian
>
> **Trigger:** Viros reaches 0 HP. The Gate Stone cracks completely. The ritual energy releases through the fracture. The water beneath the chamber floor buckles. The dragon tears through.
>
> *It was always down there. Viros didn't summon it — he was trying to bind it. It refused. Now it's free and it's in pain and it has no idea who the party is.*
>
> ### VOID GUARDIAN *(Young Blue Dragon reskin — CR 9)*
> *Void-corrupted sea guardian. Scales cracked, dark. Eyes white. Breath weapon is necrotic, not lightning. It is not evil — it is destroyed.*
>
> | | |
> |---|---|
> | **AC** | 17 (natural armour — cracked) |
> | **HP** | 110 *(reduced — wounded by the ritual)* |
> | **Speed** | 40 ft, fly 80 ft, swim 40 ft |
>
> | STR | DEX | CON | INT | WIS | CHA |
> |---|---|---|---|---|---|
> | 21 (+5) | 10 (+0) | 19 (+4) | 14 (+2) | 13 (+1) | 17 (+3) |
>
> **Saving throws:** DEX +3, CON +7, WIS +4, CHA +6
> **Damage immunities:** necrotic *(void corruption replaces lightning)*
> **Resistances:** bludgeoning, piercing, slashing from nonmagical attacks
>
> **Living Shadow:** In dim light or darkness, resistance to all damage from non-magical attacks.
>
> **Void Aura:** Creatures starting their turn within 10 ft make DC 14 Con save or have disadvantage on attack rolls until the start of their next turn.
>
> **Multiattack:** one Bite + two Claws
> **Bite** *+8* — 2d10+5 piercing + 1d6 necrotic
> **Claw** *+8* — 2d6+5 slashing
>
> **Void Breath** *(Recharge 5–6)* — 60 ft line, DC 15 Dex save. **8d8 necrotic** (half on save). Creatures that fail also have their **max HP reduced** by half the damage taken until a long rest.
>
> ---
>
> **[[Picasso]]'s Choice:** The seed is in his pocket. The Void Guardian is the powerful being in pain. He can act at any point while it lives.
> - **Plants the seed:** The void corruption recedes visibly. The dragon stills. Something vast stirs in the water far below Coffin Rock. Cthulhu has a foothold. The dragon is no longer the party's problem — but what comes next is not resolved tonight.
> - **Doesn't plant it:** The dragon must be killed. When it dies, it dissolves into dark water. Nothing stirs below. Cthulhu goes quiet.
>
> ---
>
> ## ALLIES
>
> *Keep their damage moderate. Let the party land the finishers.*
>
> ---
>
> ### SIBIL MEADOWLARK — Blood Hunter (Ghostslayer), Level 10
> **HP:** 58 | **AC:** 15 | **Attack:** +7
>
> **Start of combat — Bonus Action:**
> **Crimson Rite of the Dawn** — pay 1d8 HP (can't be reduced). Her weapon deals +1d8 radiant for the rest of the fight. One-time activation.
>
> **Each turn:**
> Two weapon attacks — +7 to hit, 1d8+4 slashing + 1d8 radiant.
> **Ghostslayer:** Undead that start their turn within 5 ft of her take her Hemocraft modifier in radiant damage automatically.
>
> **Once per combat — Bonus Action:**
> **Blood Curse of the Marked** — one creature has disadvantage on their next save; Sibil has advantage on her next attack against them.
>
> She goes straight at the biggest thing in the room. She does not take direction. She is always smiling. She will get hit a lot.
>
> ---
>
> ### ZORA MEADOWLARK — Wizard, Level 10
> **HP:** 52 | **AC:** 14 (Mage Armor) | **Spell Save DC:** 16
>
> **Round 1 — Concentration:**
> **Haste** on Sibil. Sibil gets double speed, +2 AC, advantage on Dex saves, and an extra attack every turn.
>
> **Each turn while Haste holds:**
> **Blight** — DC 16 Con save, 8d8 necrotic, half on save. She points at something and it withers.
>
> **If Haste concentration breaks:**
> **Enervation** *(new concentration)* — 8d8 necrotic on one target per turn, DC 16 Con save. On a fail, Zora heals half the damage dealt.
>
> **Once — the big one:**
> **Finger of Death** — 7d8+30 necrotic, DC 16 Con save, half on save. If it kills: the target rises as a zombie under her control next turn. Save this for a mummy or a moment that matters.
>
> She casts Haste on Sibil and then stands still and kills things. She doesn't talk during combat. If Sibil goes down, she doesn't react — she picks a new target.

---

# Scene: Epilogue — What Comes After

> [!Summary]+
> The chamber is quiet. [[Viros]] is dead. The Gate Stone is cracked or gone. The controlled folk outside are themselves again — confused, cold, missing days they can't account for. [[Zora Meadowlark]] does whatever she does next. The crew is alive.
> Go around the table. Give everyone their moment.

> [!Note]+
> **[[Picasso]]** — He made his choice. Whatever it was, it has consequences that stretch forward. If he planted the seed: something has changed in the world's water. If he didn't: Cthulhu is quiet. For now. Either way, don't resolve it here — let it sit.
>
> **[[Vel'Korr]]** — He got Varnak back, or he didn't. If he did: Varnak's last words are whatever Vel'Korr needs to hear. *"You kept her close."* Something like that. Something true. If he didn't: Vel'Korr put his father down himself. That's its own ending.
>
> **[[Faefi]]** — Elyra had one breath of clarity when Viros died. She was happy. She was free. She looked at Faefi and she knew her. Then she was gone. That's the ending Faefi didn't get to have at the abbey.
>
> **[[Kel]]** — The act of the battle, the crew alive around him, the cereal this morning — something has settled. Ask Kevin: *does Kel take his oath?* This is the moment Forgas has been waiting for. Let the player decide.
>
> **[[Soffalie]]** — The Wok-woks are calm for the first time in weeks. Thalmyre feels right to them. Ask the player: does she stay?
>
> **[[Thorne]]** *(Rachel not present — narrate)* — Her One-trek began when she left [[Heaven's Hole]]. Ask Rachel at the next opportunity: *"You've been everywhere, seen everything, sailed with this crew. Is it done? What's your plan now?"*
>
> **[[Zora Meadowlark]]** — She got what she came for, or she didn't. Either way, she doesn't linger. She looks at the party once before she goes. Whatever she says, it isn't a goodbye — it's a *see you later.*

---

# Finale

> [[The Salty Bitches]] arrived in [[The Seat of Thalmyre]] on the eve of [[Tidescrest]] — a pirate festival loud with gunpowder, greased masts, and faction banners snapping over every rooftop. They found [[Whelk's Landing]], drank with the factions, watched [[Captain Bubblebeard]] throw people across a fighting pit with the grin of a man who had no idea he was running out of time. By morning, the festival had emptied. Bubblebeard was dead in his chair, no wounds, glass eye gone. The controlled folk walked in silence toward the eastern docks. The runes on their skin pointed to [[Coffin Rock]].
>
> Below the rock, [[Viros]] stood over the cracked [[Tidemother]] Gate Stone with the [[The Red Talons|Red Talons]] at his back — [[Varnak]], [[Astra]], [[Joanos]], and three others, reanimated and still. The [[Meadowlark Sisters]] were already there, mid-argument over a deal Viros had never intended to honour. The crew descended. [[Faefi]] pushed Viros into the pit with [[Captain Bubblebeard|Bubblebeard]]'s own hand, and the Gate Stone shattered — releasing the Void Guardian, a sea dragon void-corrupted and screaming, tearing through the chamber floor. [[Thorne]] planted a magic bean beneath it. A sixty-foot pyramid erupted through the stone and impaled the dragon where it surfaced. [[Picasso]] painted [[Cthulhu]] onto the dragon's ruined skull with magic ink and was answered. The crew used what they had — including the remaining contents of a bag of beans, fired into the corpse for reasons that made sense at the time.
>
> [[Vel'Korr]] took [[Varnak]] and [[Astra]] from the chamber and saw to it that they were burned. [[Faefi]] found [[Mother Elyra]] aboard the [[The Red Talons|Red Talon]] vessel afterward, staring out at nothing. Elyra turned and looked at her — not with clarity, not with peace — and said she shouldn't have been there. That was all.
>
> [[Vel'Korr]] and [[Faefi]] left with [[Zora Meadowlark]], bound for the underdark and whatever she has waiting there. [[The Salty Bitches]] stood in the salt-damp dark, alive and victorious. [[Viros]] was dead. The Gate Stone was gone. [[Cthulhu]] had a foothold in the world.
>
> The tide, for the first time in weeks, came in on time.

