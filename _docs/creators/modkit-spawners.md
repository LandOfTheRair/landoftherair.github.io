---
title: "Modkit: Spawners"
permalink: /docs/modkit-spawners/
---

## Spawners

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
