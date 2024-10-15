---
title: GM Commands
permalink: /docs/gm-commands/
---

## About

If you're here, you're probably using the Mod Kit and running a local server where you're a GM, either to mess around or to test your own maps. This page will list out the most common, useful GM commands and how to use them. You can find a more full list [over here](https://github.com/LandOfTheRair/LandOfTheRair/tree/master/server/src/helpers/game/commands/gm).

## Lobby Commands

| Command | Usage | Description |
| ------- | ----- | ----------- |
| `/alert` | `/alert <message>` | Send an alert to all players. |
| `/ban` | `/ban <accountname>` | Ban a player. They must be online. |
| `/createevent` | `/createevent name="Test Event" duration=30 statBoost.skillBonusPercent=10 statBoost.xpBonusPercent=10` | Create an event for players. `statBoost` can contain any valid stats, and `duration` is in minutes. |
| `/creategm` | `/creategm <accountname>` | Make a player a GM. They must be online. |
| `/createtester` | `/createtester <accountname>` | Make a player a tester. They must be online. |
| `/kick` | `/kick <accountname>` | Kick a player from the game. They must be online. |
| `/lockgame` | `/lockgame` | Toggle whether or not players can get in the game. |
| `/motd` | `/motd <newmotd>` | Set the MOTD for the lobby. Passing no `newmotd` will reset it to default. |
| `/mute` | `/mute <accountname>` | Mute a player. They must be online. |
| `/redeemable` | `/redeemable <item="item name" gold=10000 forAccountName="accountname" expiresAt=timestamp maxUses=3>` | Create a redeemable item, returning the code. `item` must be a valid item id. `gold` requires a valid number. `forAccountName` will make it specifically for one person. `expiresAt` will require a timestamp (`Date.now()` can get you started). `maxUses` is the maximum number of uses a code can have (don't specify to disable this). You must pass at least `gold` or `item`. |
| `/silver` | `/silver <amount> <accountname>` | Give silver to a player. They must be online. |
| `/subscribe` | `/subscribe <days> <accountname>` | Make a player a subscriber. They must be online. |

## Game Commands

| Command | Usage | Description |
| ------- | ----- | ----------- |
| `@achievement` | `@achievement <playerish> <achievementname>` | Toggle earning an achievement for a player. |
| `@allegiance` | `@allegiance <newallegiance>` | Change your allegiance to any valid allegiance, or GM, to test aggro. |
| `@axp` | `@axp <amount>` | Gain AXP equal to the amount specified. |
| `@crash` | `@crash` | Crash the event loop for the game. |
| `@creategold` | `@creategold <amt>` | Create an amount of gold in your hand. |
| `@dupe` | `@dupe` | Duplicate your right hand to your left. | 
| `@execj` | `@execj <code>` | Evaluate JS code. You might want to read the docs on this one. |
| `@examinecreature` | `@examinecreature <targetish>` | Examine a creature's stats and other data. | 
| `@examineground` | `@examineground <itemClass?> <numSlot?> <propsish?>` | Examine an item on the ground | 
| `@examineitem` | `@examineitem` | Examine the item in your right hand. This will only show modified properties, not the base item data. |
| `@freezeai` | `@freezeai` | Freeze or unfreeze the AI for the game. |
| `@gainskill` | `@gainskill <skill> <amt>` | Gain an amount of skill to level it up. | 
| `@gaintradeskill` | `@gainskill <skill> <amt>` | Gain an amount of tradeskill to level it up. |
| `@gearup` | `@gearup <stat> <level>` | Equip the best gear for `level` based on the given `stat`.
| `@gg` | `@gg` | Quickly kill yourself. |
| `@item` | `@item <itemname>` | Create an item in your right hand. | 
| `@kill` | `@kill <targetish>` | Kill the first creature matching your target. |
| `@listplayers` | `@listplayers` | Get a list of all players by account name currently online. |
| `@modcreature` | `@modcreature <targetish> <creatureish>` | Modify the target with the properties specified; these need to be formatted in a JSON-friendly format, such as `@modcreature stats.hp=1000` |
| `@modground` | `@modground <itemClass> <numSlot> <propsish>` | Modify an item on the ground. Keep in mind that to access the item, you must modify `item.X` instead of how `@moditem` works. |
| `@moditem` | `@moditem <itemish>` | Modify the item in your right hand with the properties specified; these need to be formatted in a JSON-friendly format, such as `@moditem trait.name=CoolTrait trait.level=2` |
| `@removeeffect` | `@removeeffect <playerish> <effectname>` | Forcibly remove an effect from a player by name. |
| `@resetdungeon` | `@resetdungeon <map> <seed?>` | Reset the specified map dungeon with the given seed, or pick one if not specified. |
| `@respawnnpc` | `@respawnnpc <nameish>` | Respawn an NPC in your current map with a name that contains `nameish`. |
| `@saveplayers` | `@saveplayers` | Save all players currently in the game. |
| `@searchitems` | `@searchitems <query>` | Search the item database for items that partially match `query`. |
| `@send` | `@send <playerish> x y <map>` | Send a player in view to a specific place. |
| `@spellmod` | `@spellmod <spell/"list"> <multiplier>` | Set the global potency override for `spell` to `potency`. If `list` is specified, show all overrides. |
| `@startevent` | `@startevent <event>` | Start the given event, or stop it if it's already active. |
| `@summon` | `@summon <player>` | Summon the given player to your current location. |
| `@takeover` | `@takeover <npcish>` | Take over the NPC, allowing you to watch the NPC as if you were it. |
| `@teleport` | `@teleport <x> <y> <map?>` | Teleport to x,y on the current map. If `map` is specified, teleport to those coordinates on that map instead. |
| `@teleportto` | `@teleportto <targetish> <index>` | Teleport to the first creature or player matching your target. Specify `<index>` to teleport to a different found target. |
| `@togglemapblock` | `@togglemapblock <map>` | Block the specified map from being entered, and kick out any players in that map. |
| `@updatecontent` | `@updatecontent` | Get the latest content from GitHub and update it live. |
| `@upgradeitem` | `@upgradeitem` | Upgrade the item in your right hand using the item in your left hand. |
| `@wallsight` | `@wallsight` | Toggle being able to see through walls. |
| `@wallwalk` | `@wallwalk` | Toggle being able to walk through walls. |
| `@xp` | `@xp <amt>` | Gain an amount of XP. |
