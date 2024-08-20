---
title: Modkit Usage
permalink: /docs/modkit/
---

## Getting Started

_Unfortunately, at this time, the ModKit is Windows only. You could build it on other platforms if desired, though._

1. [Download the Modkit from GitHub](https://github.com/LandOfTheRair/mod-toolkit-v2/releases/latest/download/LandOfTheRairModdingTools.zip).
1. Unzip the archive, and run `Land of the Rair ModKit.exe`.
1. When the ModKit opens, it will download a bunch of resources. This will cover some, but not all of the resources you will need. These are the essentials to get up and running, though.

Upon completion of these steps, you should see something like this:

![](https://i.imgur.com/RrGvzFx.png)

## Loading the Base Game Content

If you want to check the base game content out, make changes or tweaks, or test it, this section is important!

If you intend to _contribute fixes back_, you should set up and install [git](https://git-scm.com/), [clone this repository](https://github.com/LandOfTheRair/Content), and have a GitHub account.

If you _only_ want to test, you can download [this file](https://github.com/LandOfTheRair/Content/blob/master/mods/BaseGameContent.rairmod).

Either way, you will have a `BaseGameContent.rairmod` file available to you. From here, Go into the Actions menu and import the mod. You can follow the rest of this guide for usage or testing as normal.

It will automatically sync changes back to this file, which you can use to easily submit pull requests on GitHub, too! 

## The Tabs

### Maps

Here, you can import or create new maps. To get started, it's recommend to hit "Create New". This will create a map with the default settings, pathing, and sprite locations set up correctly. 

Once created, you can continue to edit your maps as needed. For more help, check the [map making guide](https://rair.land/docs/map-making/).

### NPCs

NPCs are a fairly complicated interface. There's a few tabs, and a few things to know about each tab. 

#### Core Stats

![](https://i.imgur.com/jvGdn7S.png)

There are a fair few things set here by default. For example, hostility, alignment, class, allegiance, category, etc. These generally don't need to be changed.

Things that do need to be set:

- Sprite - This needs to be a multiple of 5 (each NPC sprite has 5 states, and the south-facing one is required to be used). Using the arrow keys will handle this. If you need to look up where a sprite generally is, [here is the spritesheet the game uses](https://play.rair.land/assets/spritesheets/creatures.png).
- Internal ID - This needs to be unique. A common naming scheme is `[Map Name] My NPC`, like `Rylt Renegade`.
- Level - This is the general level that players will expect to engage with this NPC. There are helpers to set HP, MP, XP, Gold, Skill on Kill and stats based on level. These don't need to be too fine-tuned but can be.
- Skill - This is the skill of the NPC. Most NPCs are not very high skill, as skill scaling is _very_ harsh.

Optional settings:

- Name - If set, the NPC will spawn with this name. 
- Affiliation - If set, the NPC will have this tagline below their name.
- Grouping - If set, the NPC will not attack NPCs in this group.
- Aquatic - If set, the NPC will only move in the water.
- Hydrophobic - If set, the NPC will not move in the water.
- No Corpse - If set, the NPC will not drop a corpse upon death.
- No Items - If set, the NPC will not drop any items upon death.

#### Traits, Spells & Attributes

![](https://i.imgur.com/OS3KXkf.png)

In the left column, you can add any existing trait to an NPC and give it a level.

In the middle column, you can add any spell to an NPC and give it a weight (see Weighting below).

In the right column, you can add any effect to an NPC for it to spawn with.

#### Gear

![](https://i.imgur.com/vhXlltm.png)

In the left column, you can add items to the NPCs sack for it to spawn with, as well as a weight (see Weighting below).

In the right column, you can add items for specific NPC gear slots for them to spawn with, based on a weight (see Weighting below). They will be wearing these items. It is common to have a "None" item that spawns most of the time, which is how NPCs get "rare" items.

#### Drops

![](https://i.imgur.com/69Ot2hK.png)

In the left column, you can add an item drop to the NPC based on weight (see Weighting below).

In the middle column, you can add a "copy drop" to the NPC. A copy drop allows you to mark an equipment slot as something the NPC should drop. For example, if the NPC rarely spawns with a cool robe in the `robe1` slot, you could add that as a copy drop and it would drop when the NPC dies. This, in combination with weighted NPC item spawning from the Gear tab, is how rare item drops work.

In the right column, you can add what item the NPC tans for, if any, and the skill required to do the tan. You can also modify the drop pool, used for some boss NPCs like Saraxa. The drop pool is guaranteed to drop between min and max items, and it will pick that many items from the item list below it.

#### Triggers

![](https://i.imgur.com/zPSGa8x.png)

In the left column, you can add "combat messages" for the NPC to randomly say during combat.

In the right column, you can create sound effects for certain triggers for the NPC. The two supported triggers currently are spawning and leashing (when the NPC goes back to its spawner).

#### Faction Reputation & Summonability

![](https://i.imgur.com/U0WPiXB.png)

In the left column, you can see the faction outlook for this NPC. This determines if they're friendly or not with other factions. This can be easily set by hitting the red/green buttons.

In the second column, you can set how much faction reputation you get for killing this NPC.

In the third column, you can add stat scaling for summoning this creature (used only by creatures that are summoned by spells).

In the fourth column, you can add skill scaling for summoning this creature (used only by creatures that are summoned by spells).

### Items

Items are fairly straightforward, as most of the fields are ones you'd recognize from interacting with them.

#### Core Stats

![](https://i.imgur.com/ZtK37bn.png)

In the left column, you can set the required settings for an item:

- Sprite - Using the arrow keys will let you traverse sprites if you don't know the number you want. If you need to look up where a sprite generally is, [here is the spritesheet the game uses](https://play.rair.land/assets/spritesheets/items.png).
- Type - All items are required to have a type. Setting the type will reset some other settings, so be cautious while setting this.

In the middle column, you can choose what stats the item boosts.

In the right column, if applicable, there will be miscellaneous settings that pertain to specific item types.

#### Traits, Effects & Requirements

![](https://i.imgur.com/jUr9bM0.png)

In the left column, you can set the pre-set trait for the item.

In the middle column, you can choose the effects that trigger when the item is used, when it hits something, when it's equipped, or when it's broken.

In the right column, you can set the required class and level for the item.

#### Miscellaneous

![](https://i.imgur.com/CIYKBBe.png)

Here, you can choose the cosmetic for an item. If the "Permanent Cosmetic" checkbox is checked, the cosmetic _can not_ be taken out of the item. This should be checked for most items.

### Droptables

![](https://i.imgur.com/ucC2z9D.png)

After creating at least one map and one item, you can add Droptables. These are how players get map- or region-based loot.

You can choose either a map or region drop (based on the maps you've created), an item (based on your items), a chance to drop (if you set it to 100, it will drop 1/100 of the time), whether the player luck bonus should be used (this makes it easier to find items), and if the item only drops on a certain holiday. You can also choose if it should be a global droptable, which means it will show up in every region.

### Recipes

![](https://i.imgur.com/fax97QJ.png)

After creating at least one item, you can add Recipes, which are used by tradeskills to let players refine items into other items.

Recipes have a lot of options that can be set, but the important ones are:

- Name - This is the recipe name displayed in game, and must be unique.
- Item - The resulting item when the recipe is crafted.
- Tradeskill - The tradeskill used by the recipe.
- Category - The in-game display category for the tradeskill.

Other options:

- Min/Max Skill - The skill range required to craft this item.
- Skill+/XP+ - The rewarded XP/Skill for crafting this item.
- Required Class - The required class for crafting this item.
- Required Spell - The required spell for crafting this item.
- Must Learn - If checked, this must be learned from a recipe book.
- Skill -> Potency - If checked the potency of the created item is copied from the tradeskill skill level of the user.
- Transfer Owner - If set, will transfer the owner of the specified item to the resulting item, allowing third parties to utilize those items and craft for someone else.

Ingredient options:

- Ing #1-8 - The item required for crafting.
- #1-2 Item Filter - The item name to "filter for" (for small and large copper, you would set it to Copper Ore)
- #1-2 Visual - The item visual for the filter (this is an item name, like Copper Ore (Small)
- #1-2 Ounces - The number of ounces required from the items for the forge

### Spawners

![](https://i.imgur.com/MUFSE4o.png)

After adding NPCs, you can add spawners for them to utilize in a map. There are a lot of properties here to consider, but most of them should be fairly straightforward:

- Tag - This is what you set the Tag to for the spawner object on the map to link them together.
- Respawn Rate (sec) - The number of seconds it takes to respawn this spawner.
- Spawn Radius - The number of tiles outwards that can spawn NPCs. Recommended no more than 2-3.
- Walk Radius - The number of tiles outwards the NPCs can walk / follow players.
- Leash - The number of tiles before the NPC will forcibly leash back to its spawner (must be greater than walk radius)
- Initial Spawn - The number of NPCs spawned immediately when the spawner is created
- Max Spawn - The maximum number of NPCs that can be active for this spawner at one time.
- Holiday - The required holiday for this spawner to trigger.
- Elite Tick Cap - The number of NPCs that must spawn before an Elite can spawn.
- Always Spawn - If checked, this spawner will always spawn an NPC regardless of whether or not the map is at cap. Used primarily for "important" spawns (bosses, quests, etc).
- Should Save - If checked, the respawn timer will persist between map loads. Used primarily for "important" spawns (bosses, quests, etc).
- Require Dead To Respawn - If checked, this spawner will not spawn anything new until every creature on it is dead. Primarily used for bosses to prevent duplicates.
- Respect Knowledge - If checked, this spawner will not be active unless there is a player nearby.
- Paths - If set, NPCs will walk along a path instead of randomly. This can be used to direct NPCs into certain areas, or patrol certain areas.

In the middle column, there are some primarily-boss focused options:

- Make Lair-like Spawner - **be careful** as this is a one-way option, and not reversible. This will make your spawner "lair-like" and pre-set the useful settings for boss creatures.
- Attribute Add Chance - The likelihood of a custom attribute (berserk, lucky, etc) being added to the NPCs that spawn here.
- Strip Radius - If this NPC strips (Should Strip is checked), this number is the radius by which it scatters items randomly.
- Strip X/Y - If set (and Should Strip is checked), this NPC will strip to this X/Y instead of where the player dies.
- Eat Tier - If set, this NPC will "eat" the players skill and XP. The scaling is 5% per tier, so tier 1 means 5% XP and skill lost.
- Dangerous Creatures - If set, creatures that spawn from this spawner will get the Dangerous buff.
- Should Strip - If set, creatures that spawn from this spawner will strip players.
- Strip On Spawner - If set, creatures that spawn from this spawner will strip back to their spawner. **warning** this option is very mean!

The right column lets you choose NPCs to spawn at this spawner, based on weight (see Weighting below).

### Quests

![](https://i.imgur.com/wmvYuJG.png)

In the left column, you can set the quest name, description, and giver. The description and giver are display only for the in-game quest log. You can also toggle whether the quest is a repeatable quest (you can repeat it immediately upon completion) or a daily quest (you can do it at most once per day).

In the middle column, you can set the quest type, and all variables related to that. Most quests will either be "none", "item", or "kill".

In the right column, you can choose the rewards for the quest.

### NPC Scripts

When making an NPC Script, there are a few tabs, although two of them will eventually be updated to support a friendlier UX for users. All the same:

#### Core Stats

![](https://i.imgur.com/d9XQRPR.png)

The most important thing here to set is the Map NPC Tag, which determines which NPC to bind this script to on the map. Everything else set here is handled the same as in the NPC editor.

#### Behaviors

![](https://i.imgur.com/dYeQM7r.png)

Here, you have to write YAML for your NPC behaviors. The most common NPC behaviors will be shops, but there are examples for everything! Check [here](https://github.com/LandOfTheRair/LandOfTheRair/tree/master/server/src/models/world/ai/behaviors) for a listing of behaviors, and you can find examples by searching [here](https://github.com/LandOfTheRair/Content/tree/master/npcScripts).


#### Dialog

![](https://i.imgur.com/2XwfzDk.png)

Here, you have to write YAML for your NPC dialogs. This can be as detailed as you would like, but should be copy-pastable from other examples found [here](https://github.com/LandOfTheRair/Content/tree/master/npcScripts). When in doubt, ask!

### The Menu

![](https://i.imgur.com/JwgkHEU.png)

Most of this menu will be straightforward, but there are some important details to know about certain options. Only those options will be covered:

#### Differences Between Load, Save, and Export Mod

Load and Save mod are used to work with a user-readable version of the mod. This is the format the modkit tools understand.

Export mod is used to create a version of the mod that Land of the Rair understands.

The process for submitting these mods are not yet finalized, but will likely be something along the lines of "submit a certain file", which will be the result of "export".

#### Mod Testing

When testing your mod (which you should!), you will first need to hit "Install MongoDB..." and "Install Rair Server..." to download and install the executable server code, as well as a database. The total download will be ~370mb (which is why it's not done at startup).

After this, you can Test Mod, which will let you actually get in there and test your maps, content, etc.

![](https://i.imgur.com/GbuoWHC.png)

On the left side, you can set the level, map, x/y to force upon all characters for really quick testing. On the right side, you could set "extra" properties if you knew the property you wanted to set. For example, you could set it so any time you log in, you are also the "GM" allegiance, which makes you neutral to all creatures. To do this, you would set the Extra Character Settings to: `{ "allegiance": "GM" }`.

If you have the open client option checked, it will open a new instance of the client pointing to your local server. You generally don't want to open more than one client as it will kick you out of the others.

You can also kill all database and server processes running, if for some reason they're lingering around.

Once you get into the game, you can use GM commands to tweak, summon, or otherwise test your mod. You can [find more information on that here](https://landoftherair.github.io/docs/gm-commands/).

#### Update Resources

This option retrieves all spritesheets, template maps, and configuration data in the base Land of the Rair game (effects, spells, etc) for usage with the editor. If there are ever new spells that you would like to use in your mod, but don't have them, update resources to obtain them.

## FAQ

Here are some frequently asked questions that may have come up while reading this page.

### What is Weighting?

When there is a "weight", that means that all options in the list will be "weighted" against each other when picking from that list. If you have 3 entries with weights 1, 1, and 1 they are all equal weight, and all likely to be picked. However, if you have entries with weight 3 and 1, then the first entry is 3 times as likely to be picked. 

In this editor, there is also the ability to specify -1 as a weight, which means "always" (in certain contexts). If there are ever two inputs (as with NPC drops, and NPC sack), the left one will be "chance" and the right one will be "max chance" - set chance to -1 to ensure it always appears or drops (max chance can be set to anything). Otherwise, it will be a chance / maxChance of appearing (usually, you would set chance to 1, and maxChance to something like 100 for a 1/100).

In some cases, it is preferred to not use the -1 notation, and instead have a "none" result (this is the case with all NPC equipment). It is possible that this will one day be made homogenous; but that is not how it exists today.

Sometimes, there is also a "max chance" option next to a weight, or the option itself functions as "max chance" instead of "weight". In this case, the option will not be weighted, but instead will drop in a 1/max chance.
