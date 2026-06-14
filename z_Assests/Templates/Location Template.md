<%*
let title = tp.file.title || await tp.system.prompt("Location Name");

const categories = [
    "Planet", "Continent", "Region", "Waterbody", "Island", "Nature",
    "City", "Town", "Village", "Port",
    "Tavern", "Shop", "Temple", "Government", "House", "Ruin", "Dungeon",
    "Add new category..."
];
let category = await tp.system.suggester(categories, categories, false, "Location Category");
if (category === "Add new category...") {
    category = await tp.system.prompt("Enter new category name:");
}
-%>
---
Type: Location
Location_Category: <% category %>
Location:
Place_Description:
---
# [[<% title %>]]

> [!warning]
> Reminder to move to appropriate folder: root saves in /World (Erodas)

## Description


## Places Within
```dataview
TABLE Location_Category, Location, Place_Description
WHERE Type = "Location" AND contains(Location, this.file.link)
```

## Notable NPCs
```dataview
TABLE Location, Species, Faction
WHERE (Type = "NPC" OR Type = "PC") AND contains(Location, this.file.link)
```
