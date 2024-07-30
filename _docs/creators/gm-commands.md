---
title: GM Commands
permalink: /docs/gm-commands/
---

## About

If you're here, you're probably using the Mod Kit and running a local server where you're a GM, either to mess around or to test your own maps. This page will list out the most common, useful GM commands and how to use them. You can find a more full list [over here](https://github.com/LandOfTheRair/LandOfTheRair/tree/master/server/src/helpers/game/commands/gm).

## Commands

| Command | Usage | Description |
| ------- | ----- | ----------- |
| `@allegiance` | `@allegiance <newallegiance>` | Change your allegiance to any valid allegiance, or GM, to test aggro. |
| `@axp` | `@axp <amount>` | Gain AXP equal to the amount specified. |
| `@crash` | `@crash` | Crash the event loop for the game. |
| `@creategold` | `@creategold <amt>` | Create an amount of gold in your hand. |
| `@dupe` | `@dupe` | Duplicate your right hand to your left. | 
| `@execj` | `@execj <code>` | Evaluate JS code. You might want to read the docs on this one. |
| `@examinecreature` | `@examinecreature <targetish>` | Examine a creature's stats and other data. | 
| `@examineitem` | `@examineitem` | Examine the item in your right hand. This will only show modified properties, not the base item data. |
| `@freezeai` | `@freezeai` | Freeze or unfreeze the AI for the game. |
| `@gainskill` | `@gainskill <skill> <amt>` | Gain an amount of skill to level it up. | 
| `@gaintradeskill` | `@gainskill <skill> <amt>` | Gain an amount of tradeskill to level it up. |
| `@gg` | `@gg` | Quickly kill yourself. |
| `@item` | `@item <itemname>` | Create an item in your right hand. | 
| `@kill` | `@kill <targetish>` | Kill the first creature matching your target. |
| `@modcreature` | `@modcreature <targetish> <creatureish>` | Modify the target with the properties specified; these need to be formatted in a JSON-friendly format, such as `@modcreature stats.hp=1000` |
| `@moditem` | `@moditem <itemish>` | Modify the item in your right hand with the properties specified; these need to be formatted in a JSON-friendly format, such as `@moditem trait.name=CoolTrait trait.level=2` |
| `@resetdungeon` | `@resetdungeon <map> <seed?>` | Reset the specified map dungeon with the given seed, or pick one if not specified. |
| `@saveplayers` | `@saveplayers` | Save all players currently in the game. |
| `@searchitems` | `@searchitems <query>` | Search the item database for items that partially match `query`. |
| `@spellmod` | `@spellmod <spell|"list"> <multiplier>` | Set the global potency override for `spell` to `potency`. If `list` is specified, show all overrides. |
| `@startevent` | `@startevent <event>` | Start the given event, or stop it if it's already active. |
| `@summon` | `@summon <player>` | Summon the given player to your current location.
| `@teleport` | `@teleport <x> <y> <map?>` | Teleport to x,y on the current map. If `map` is specified, teleport to those coordinates on that map instead. |
| `@teleportto` | `@teleportto <targetish>` | Teleport to the first creature or player matching your target. |
| `@togglemapblock` | `@togglemapblock <map>` | Block the specified map from being entered, and kick out any players in that map. |
| `@updatecontent` | `@updatecontent` | Get the latest content from GitHub and update it live. |
| `@upgradeitem` | `@upgradeitem` | Upgrade the item in your right hand using the item in your left hand. |
| `@wallsight` | `@wallsight` | Toggle being able to see through walls. |
| `@wallwalk` | `@wallwalk` | Toggle being able to walk through walls. |
| `@xp` | `@xp <amt>` | Gain an amount of XP. |
