---
dg-publish: true
Type: Species
---
# [[Aasimar]]

Aasimar are mortals touched by celestial heritage — the result of divine bloodlines filtering down through generations, manifesting as an inner radiance that sets them apart from ordinary folk.

## Description

Aasimar carry the mark of something beyond the mortal world. They tend toward striking appearances — pale or luminous skin, silver or gold-flecked eyes, hair that catches light strangely. Their celestial nature grants them minor divine abilities that develop over time, though the form these take varies widely between individuals.

In most of [[Erodas]], Aasimar are rare and unremarkable in cultural terms — individuals with unusual gifts and no shared identity. The exception is [[Goghdor]].

## The Star Touched of Goghdor

On [[Goghdor]], Aasimar — both elven and dwarven — are known as the **Star Touched**, and their celestial nature is the foundation of an entire culture. Here, the divine heritage is not an accident of birth but a calling. Star Touched communities live across [[Goghdor]]'s mountainside, bound not by governance but by shared tradition.

Aasimar encountered outside of [[Goghdor]] do not typically identify as Star Touched. The blood may be the same; the meaning made of it is not.

## The Ascent

The defining rite of passage for every Star Touched is the **Ascent** — a solo climb up [[Goghdor]] through the perpetual clouds to the open sky above. There is no set age and no ceremony of departure. You go when you feel ready.

Above the cloud line, the stars become visible for the first time. The constellations respond to the climber's presence, and a **[[Skoldrún]]** manifests — a constellation spirit in animal form that becomes bound to the individual for life. The Skoldrún is understood as a gift from the mountain and the sky: the shape of the climber's purpose, given form.

Those who have not yet made the Ascent are considered unfinished, not lesser. What Skoldrún one receives is private — its meaning belongs to the individual alone.

## The Rearrangement

The Star Touched hold a deep and ancient prophecy: one day, a Star Touched individual of immeasurable power will rise and **rearrange the constellations themselves** — reshaping the sky and throwing the world into profound imbalance. This event is called **The Rearrangement**.

The constellations are not merely stars to the people of [[Goghdor]]. They are the architecture of fate, the source of the [[Skoldrún]], the structure that gives the Star Touched their purpose. To rearrange them would be to unmake the order of all things — to strip meaning from every Ascent ever made and plunge [[Erodas]] into an age without direction.

Whether The Rearrangement is prophecy, warning, or inevitability is debated quietly among Star Touched elders. What is not debated is that it must be prevented.

## Culture and Society

Star Touched communities are autonomous and scattered across [[Goghdor]]'s slopes. There is no central ruler. Elders carry the most weight within their own communities, and a small council of the oldest and most experienced among them — the **[[Elder Council of Goghdor]]** — observes the broader traditions of the mountain and keeps the old knowledge.

The **[[The Astral Volley]]** is the most significant event of the Star Touched year — the three nights when the sky fills with light and the [[Skoldrún]] burn brightest. It is the most common time for the Ascent, and the only occasion when most of [[Goghdor]]'s communities gather together.

```dataviewjs
dv.header(2, "Notable " + dv.current().file.name);
dv.table(["Location", "Faction"], 
  dv.pages()
    .where(p => (p.Type === "NPC" || p.Type === "PC") && p.Species && dv.array(p.Species).some(s => s && s.path === dv.current().file.path))
    .map(p => [p.file.link, p.Location, p.Faction])
);
```
