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
| `@creategold` | `@creategold <amt>` | Create an amount of gold in your hand. |
| `@dupe` | `@dupe` | Duplicate your right hand to your left. | 
| `@examinecreature` | `@examinecreature <targetish>` | Examine a creature's stats and other data. | 
| `@examineitem` | `@examineitem` | Examine the item in your right hand. This will only show modified properties, not the base item data. |
| `@gainskill` | `@gainskill <skill> <amt>` | Gain an amount of skill to level it up. | 
| `@gaintradeskill` | `@gainskill <skill> <amt>` | Gain an amount of tradeskill to level it up. |
| `@item` | `@item <itemname>` | Create an item in your right hand. | 
| `@kill` | `@kill <targetish>` | Kill the first creature matching your target. |
| `@moditem` | `@moditem <itemish>` | Modify the item in your right hand with the properties specified; these need to be formatted in a JSON-friendly format, such as `@moditem trait.name=CoolTrait trait.level=2` |
| `@teleport` | `@teleport <x> <y> <map?>` | Teleport to x,y on the current map. If `map` is specified, teleport to those coordinates on that map instead. |
| `@teleportto` | `@teleportto <targetish>` | Teleport to the first creature or player matching your target. |
| `@xp` | `@xp <amt>` | Gain an amount of XP. |
