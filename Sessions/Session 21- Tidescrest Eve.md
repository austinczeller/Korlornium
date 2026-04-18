---
dg-publish:
Type: Session
date: 2026-04-08
fc-start: 12004-02-35
fc-end: 12004-02-37
fc-category: Session
Location:
  - "[[The Seat of Thalmyre]]"
  - "[[Whelk's Landing]]"
Plot_Lines:
  - "[[Breaking the Chain]]"
  - "[[The Search for Tidemother Gate Stone]]"
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
> Picasso looks at the glass. The bioluminescence on the far wall has gone dark in one section. The sand is bare. And then, at the very edge of the black water, something enormous and white drifts into view — slow, deliberate — and it turns one vast pale eye directly at him.
>
> **The bar disappears.**
>
> He is in open water. Cold, absolute pressure, no sound except a low hum he feels in his sternum. [[Cthulhu]] is in front of him — massive, luminous, tentacles spread wide in what is unmistakably a greeting. It is *thrilled*. It drifts toward him with the energy of something that has been waiting.
>
> It doesn't speak. It shows him things — impressions, not images. A great chain, slack and crumbling. A light far below the ocean floor, guttering like a candle about to go out. Something immense and ancient at the center of it, dimming. The [[Tidemother]]. Dying.
>
> Then Cthulhu turns that eye back on Picasso. The tentacles spread wider. The hum in his chest becomes a full-body pressure. The impression it pushes into him is unmistakable, delivered with the enthusiasm of a dog dropping a dead bird at your feet:
>
> *This place will need something new. I could do it. Isn't that wonderful? Aren't you glad I told you?*
>
> **Back in the bar.** Dry. In his seat. The conversation around him hasn't stopped. Nobody noticed. [[Darla Murdinthe]] is staring at the dark section of glass behind Picasso's head. When he turns, there's nothing there. She looks at him — just for a moment, Sea-folk eyes flat and unreadable — then goes back to drying the cup.
>
> [[Sliver]] stays under the table for the rest of the night.
>
> **What Picasso knows (or suspects):** Something divine is failing. The tides are its symptom. And his patron is volunteering for the vacancy.
>
> **DM note:** Don't prompt Duncan to share this. Let him decide if, when, and how Picasso tells anyone.

> [!Description]+
> A Rattails pirate two tables over slaps the table and laughs so hard he spills his ale:
> *"— and they walk in all serious, right, the wizard's got this long coat, real fancy, and his crew — I swear on Tidemother's teeth — his crew are DEAD. Like, walking, but wrong. Arms hanging. Eyes forward. Six of them. Seven maybe."*
> His friend: *"They register?"*
> *"Oh yeah. Brawl and the race. Going to be the best Tidescrest in years."*

> [!Quote]+
> If Vel'Korr approaches and asks for a description of the wizard:
> *"Elf. Real pale, even for an elf. Long coat, dark red — or maybe it's just the blood. Has a rod of some kind on his belt, looked like it had — I dunno — fingers? Walked in like he owned the place. You know him?"*

---

# Scene: Tidescrest — The Events

> [!Summary]+
> The tournament runs across two days. The party has registered tonight; tomorrow the events begin. Each event is sponsored by a gang — winning gets the party a private audience with that gang's rep. **The Brawl is the path to [[Captain Bubblebeard]].**
> [[Viros]] and his reanimated crew are competing. He doesn't know the party is here yet — or if he does, he isn't showing it.

> [!Note]+
> **Structure:** Run whichever events the players signed up for. Each is a short scene with one or two meaningful checks. Don't roll every event to death — give each a decision point and a consequence.
> 
> **If the party wins an event, they get:**
> - Access to a private sit-down with the sponsoring gang's rep (intelligence, rumors, possible alliance)
> - Crowd recognition — they become known in The Seat overnight
>
> **If Viros wins The Brawl before the party:** Bubblebeard's rep will still see the party *if* they place second — but the meeting is shorter and less friendly.

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

## Cannon Shot *(The Drifting Bastards)*

> [!Description]+
> Four cannons line the dock facing the bay. Floating targets drift on the current — barrels painted in gang colours, a stuffed dummy in a hat, what appears to be a small occupied rowboat (it isn't — probably). The crowd bets heavily and boos any miss.

> [!Note]+
> Run by the [[The Drifting Bastards]]. If the party confronted **Crunch** last night, he is personally loading the cannons and watching with great interest.
> Each contestant gets **3 shots**. Highest hit count wins. Ties broken by a sudden-death fourth shot.

> [!Challenge]+
> **Three shots. Each shot: Dexterity check (ranged attack roll) vs. target AC.**
> | Target | AC | Points |
> |---|---|---|
> | Barrel (stationary) | 12 | 1 pt |
> | Dummy (slow drift) | 14 | 2 pts |
> | The rowboat (fast drift, moving) | 16 | 3 pts |
>
> Contestants can choose which target to aim at each shot.
> - **5–6 pts:** Win. Crunch claps once, very slowly. Drifting Bastards rep acknowledges the crew.
> - **3–4 pts:** Respectable. Crowd impressed, a few bets pay out.
> - **1–2 pts:** Polite applause.
> - **Nat 1 on any shot:** The ball goes somewhere wrong. Improvise — the dummy's hat flies off, a barrel full of fish explodes, the crowd scatters.

---

## Boarding Run *(The Rattails)*

> [!Description]+
> A decommissioned ship hull has been dragged onto the main square and rigged with dangling ropes, swinging boom arms, a tilting gangplank, and halfway up — a net full of angry crabs controlled by [[Tompkins 'The Squealer' Longtooth]] via a hand-crank. He is grinning. He has been waiting for this all year.

> [!Note]+
> Up to **4 contestants** run simultaneously, competing for fastest time.
> Each **failed check adds 1 round** to that contestant's time. Lowest total time wins.
> Squealer will absolutely deploy the crab net early on whoever he finds funniest.

> [!Challenge]+
> **Three stages in sequence — all contestants run at the same time.**
> | Stage | Check | DC | Failure |
> |---|---|---|---|
> | Hull climb | Athletics | 12 | +1 round, must retry next turn |
> | Rope swing past the boom | Acrobatics | 13 | +1 round, swinging obstacle hits you |
> | Crab net & final scramble | Strength or Athletics | 11 | +1 round, crabs. Just crabs. |
>
> - **0 failures (3 rounds):** Win. Squealer screams your name at the crowd. Rattails after-party invitation.
> - **1 failure (4 rounds):** Strong second. Crowd cheers.
> - **2+ failures:** You finish. Eventually. The crabs may or may not still be attached.
> **Wild card:** Squealer can deploy the net at any time as a reaction (his choice, once per run). If he likes you, he waits. If you beat his crew member in a prior event, he does not wait.

---

## The Painted Plank *(Murky Bellows, co-sponsor)*

> [!Description]+
> Each contestant receives a piece of driftwood roughly the size of a shield and a set of pigments — sea-ink, crushed coral, charcoal, and something rust-red that nobody asks about. One hour. Crowd votes by tossing coins at their favourite piece. Loudest coin pile wins.
> Most entries are violent or obscene. Both are popular. Anything unexpected draws a crowd.

> [!Note]+
> No wrong answers here — reward players who describe what their character actually paints. Good descriptions should get advantage or auto-succeed.
> **NPC competition:** A quiet Murky Bellows sailor enters a meticulous painting of a ship sinking in absolute silence — unsettling, technically impressive. DC to beat him is 14.

> [!Challenge]+
> **Step 1 — Create:** Performance or Charisma check to determine quality.
> | Roll | Result |
> |---|---|
> | 8 or below | Technically a painting |
> | 9–12 | Solid. Crowd pays attention |
> | 13–15 | Impressive. Draws a crowd before judging |
> | 16–18 | People are talking about it |
> | 19+ | Someone offers to buy it immediately |
>
> **Step 2 — Crowd vote:** Opposed Charisma (Performance) vs. the Murky Bellows sailor (**+5**). Ties go to the louder coin toss.
>
> - **Win:** A [[Murky Bellows]] elder takes the plank and says it will hang in their hall. The party has a name in their books.
> - **Lose:** Still respected. The Murky Bellows sailor shakes hands without speaking and leaves.
> **Wild card:** Someone in the crowd — well-dressed, not a pirate — offers **50gp** for the plank regardless of who wins. They won't say why. They represent the [[The Blackwake Company]].

---

## The Sailing Race *(The Blackwake Company)*

> [!Summary]+
> Team event. One vessel races a circuit around the outer isles of [[Thalmyre]] and back to the main dock. The party can enter [[The Salty Bitch]]. [[Viros]]'s crew is in this race aboard a sleek black-hulled ship. The reanimated Red Talons are eerily efficient sailors — they don't tire, don't panic, and don't speak.

> [!Note]+
> This is the first chance the party gets to *see* Viros up close — he stands at the prow. He hasn't looked at them yet.
> **3 competing ships total:** The Salty Bitch, Viros's ship (*The Pale Meridian*), and a [[The Blackwake Company]] racing vessel.
> The race runs **4 legs**, each requiring a different skill. Different crew members should each contribute one check — this is a team event.

> [!Challenge]+
> **Group skill challenge: 3 successes before 2 failures.**
> | Leg | Skill Options | DC | Hazard on Fail |
> |---|---|---|---|
> | Open water sprint | Athletics or Dexterity (rigging) | 13 | Lose 1 position |
> | Navigation through Knife Gap | Survival or Perception | 14 | Risk reef damage — Salty Bitch takes 1d6 hull strain |
> | Weather the squall | Dexterity or Strength | 12 | Crew member takes 1d4 bludgeoning, lose momentum |
> | Final approach to dock | Dexterity or Charisma (coordinating crew) | 13 | Lose 1 position |
>
> - **Win (3 successes):** [[The Blackwake Company]] rep offers a private meeting — trade, intel, or passage. Viros's ship comes in second. He watches the Salty Bitch dock and says nothing.
> - **Second (lose to Viros):** His crew disembarks in silence. Vel'Korr can see Viros's face clearly for the first time. Eye contact is possible.
> - **Third:** The race is humbling. The Blackwake Company rep barely acknowledges you.

> [!Description]+
> *Viros's ship, the Pale Meridian:*
> The reanimated crew of [[Viros]]'s ship works without a word. No orders called, no reaction to the wind. They simply *adjust* — in unison, like a single organism. One of them near the stern — missing half a jaw, wearing the tattered remnants of a red coat — turns to face [[The Salty Bitch]] as you pass alongside. The jaw is gone. The eyes track.

---

## The Brawl *(The Stray Dogs — path to Bubblebeard)*

> [!Summary]+
> Elimination bracket, one-on-one, non-lethal (officially). The winner earns a private audience with [[The Stray Dogs]]' representative — and through them, a meeting with [[Captain Bubblebeard]].
> [[Viros]] has entered a reanimated Red Talon. It doesn't feel pain, doesn't tire, and doesn't stop unless destroyed.

> [!Note]+
> The bracket runs **three rounds** leading to the final. Run each as a short combat encounter using the stat blocks below.
> Non-lethal rules enforced by a Stray Dogs referee with a very large mallet. Anyone who kills their opponent is disqualified and ejected — the crowd hates it, and Darla is watching.
> The **final opponent is a Red Talon Viros reanimated** — one Vel'Korr would recognize. Vel'Korr's spotlight: does he realize who it is before the fight starts?

> [!Description]+
> The fighting ring is a circle of sand in the main square, roped off with anchor chain. The crowd is three deep. [[Tompkins 'The Squealer' Longtooth]] is somewhere in the back screaming. The [[The Stray Dogs]] rep — a scarred, quiet man in a long coat, bite mark visible on his neck — watches from a raised platform without expression.

---

### Bracket Round 1 — Grist the Stomper

*Medium Humanoid (Half-Orc), Unaffiliated*
A seven-foot half-orc with no gang colours and a smile missing three teeth. Fights for the love of it.

| HP | AC | Speed | Initiative |
|----|-----|-------|------------|
| 32 | 13 | 30 ft | +1 |

| STR | DEX | CON | INT | WIS | CHA |
|-----|-----|-----|-----|-----|-----|
| +4 | +1 | +2 | -1 | +0 | -1 |

**Actions**
- **Haymaker.** *Melee Attack:* +6 to hit, 1d8+4 bludgeoning (non-lethal).
- **Reckless Swing (Recharge 5–6).** Makes attack with advantage. Until start of next turn, all attacks against Grist also have advantage.

**Bonus Action**
- **Second Wind (1/encounter).** Heals 1d10+3 HP.

**Traits**
- *Relentless Endurance (1/encounter):* When reduced to 0 HP, drops to 1 HP instead. Grins about it.

---

### Bracket Round 2 — Tael Whisper

*Small Humanoid (Goblin), The Rattails*
A Rattails fighter who treats the rules as suggestions and the referee as an obstacle.

| HP | AC | Speed | Initiative |
|----|-----|-------|------------|
| 22 | 14 | 30 ft | +4 |

| STR | DEX | CON | INT | WIS | CHA |
|-----|-----|-----|-----|-----|-----|
| -1 | +4 | +1 | +1 | +0 | +2 |

**Actions**
- **Quick Strike.** *Melee Attack:* +6 to hit, 1d4+4 bludgeoning (non-lethal).
- **Sucker Punch (1/round).** After landing Quick Strike, bonus attack: +6, 1d4+4. On hit, target makes **DC 12 Con save** or is **blinded** until end of their next turn (sand, spit, a well-timed thumb).

**Bonus Action**
- **Nimble Escape.** Disengage or Hide.

**Traits**
- *Dirty Fighter:* If the target is distracted, flanked, or prone, Tael has advantage on their next attack roll.

---

### Bracket Semi-final — Morda "The Anchor"

*Large Humanoid (Human), Murky Bellows*
A veteran brawler who has never been knocked down. Doesn't need to hit you hard — just needs to hold you.

| HP | AC | Speed | Initiative |
|----|-----|-------|------------|
| 45 | 12 | 25 ft | -1 |

| STR | DEX | CON | INT | WIS | CHA |
|-----|-----|-----|-----|-----|-----|
| +5 | -1 | +3 | -1 | +1 | +0 |

**Actions**
- **Slam.** *Melee Attack:* +7 to hit, 1d10+5 bludgeoning (non-lethal).
- **Grapple.** Replaces one attack. Contested STR vs STR/DEX. **Escape DC 15.**

**Bonus Action**
- **Ground and Pound.** While a target is grappled: deals 1d6+5 bludgeoning (non-lethal) as a bonus action.

**Traits**
- *Unbreakable Grip:* Disadvantage on escape attempts from Morda's grapple.
- *Brawler's Fortitude:* Resistance to bludgeoning damage from unarmed strikes.

---

### Bracket Final — The Revenant *(Red Talon, Reanimated by Viros)*

*Medium Undead (Human), controlled by [[Viros]]*
A former member of [[The Red Talons]]. Vel'Korr recognizes the red talon tattoo on the neck. The broken nose. The coat — or what's left of it. It doesn't recognize him back.

| HP | AC | Speed | Initiative |
|----|-----|-------|------------|
| 58 | 14 | 30 ft | +2 |

| STR | DEX | CON | INT | WIS | CHA |
|-----|-----|-----|-----|-----|-----|
| +4 | +2 | +2 | -4 | -2 | -3 |

**Condition Immunities** Frightened, Charmed, Poisoned, Exhaustion

**Actions (Multiattack)**
- **Dead Man's Fist ×2.** *Melee Attack:* +6 to hit, 1d6+4 bludgeoning (non-lethal). Attacks twice per turn.

**Reactions**
- **Undying Drive (1/encounter).** When reduced to 0 HP, makes a **DC 13 Con save**. On success, rises to 1 HP. The referee's mallet doesn't stop it the first time.

**Traits**
- *No Pain Response:* Immune to effects requiring a pain reaction. Spells or abilities that impose conditions via pain don't function.
- *Forward Pressure:* No tactics. Moves directly at the nearest opponent and attacks. Every turn. Never retreats.
- *Recognizable:* Vel'Korr spotlight — can he keep it together long enough to win?

> [!Quote]+
> *If Vel'Korr recognizes the Revenant before the fight:*
> It takes its fighting stance. No warmup, no breath, no expression. The red talon tattoo on its neck has gone grey. Somewhere at the edge of the crowd, a pale elf in a long dark coat watches with the polite interest of someone checking the weather.
>
> **If Vel'Korr wins:** A [[The Stray Dogs|Stray Dogs]] crew member with a bite scar down his cheek approaches and says:
> *"Bubblebeard will see you. Tomorrow evening, after the closing ceremony. Come to the Stray Dogs' hall on Bent Peter. Don't bring weapons."*

---

# Scene: The Hook — Viros Leaves First

> [!Summary]+
> Whether or not the party has confronted Viros, at the end of the tournament's first day he disappears. He didn't come to Thalmyre for the tournament. He came for something else — and now he's gone into the city.
> End the session here or use this as a pressure valve to close the night and open the next.

> [!Note]+
> Don't resolve the Viros thread this session. Let it breathe. The party now knows he's here, they know he's using the Red Talons, and they don't know what he's after in Thalmyre.
> If the party won The Brawl: They have their Bubblebeard meeting tomorrow. The gate stone is close.
> If they didn't: They need another path — Darla might know something, or a Hydra gang rep might broker it for a favor.

> [!Description]+
> By the time the last Brawl bout ends, Viros's ship is gone from the dock. The black hull, the silent crew, the red coat — all of it, slipped out on the evening tide while the crowd was watching the fight. Tumbo, when asked, just shrugs. *"Paid his fee. Not my business where he goes."*
> Somewhere in [[Thalmyre]], [[Viros]] is looking for the same thing you are.
