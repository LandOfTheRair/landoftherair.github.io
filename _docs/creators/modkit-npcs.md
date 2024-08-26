---
title: "ModKit: NPCs"
permalink: /docs/modkit-npcs/
---

### NPCs

NPCs are a fairly complicated interface. There's a few tabs, and a few things to know about each tab.

### Core Stats

![](https://i.imgur.com/jvGdn7S.png)

There are a fair few things set here by default. For example, hostility, alignment, class, allegiance, category, etc. These generally don't need to be changed.

Things that do need to be set:

- Sprite - This needs to be a multiple of 5 (each NPC sprite has 5 states, and the south-facing one is required to be used). Using the arrow keys will handle this.
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

### Traits, Spells & Attributes

![](https://i.imgur.com/OS3KXkf.png)

In the left column, you can add any existing trait to an NPC and give it a level.

In the middle column, you can add any spell to an NPC and give it a weight (see Weighting below).

In the right column, you can add any effect to an NPC for it to spawn with.

### Gear

![](https://i.imgur.com/vhXlltm.png)

In the left column, you can add items to the NPCs sack for it to spawn with, as well as a weight (see Weighting below).

In the right column, you can add items for specific NPC gear slots for them to spawn with, based on a weight (see Weighting below). They will be wearing these items. It is common to have a "None" item that spawns most of the time, which is how NPCs get "rare" items.

### Drops

![](https://i.imgur.com/69Ot2hK.png)

In the left column, you can add an item drop to the NPC based on weight (see Weighting below).

In the middle column, you can add a "copy drop" to the NPC. A copy drop allows you to mark an equipment slot as something the NPC should drop. For example, if the NPC rarely spawns with a cool robe in the `robe1` slot, you could add that as a copy drop and it would drop when the NPC dies. This, in combination with weighted NPC item spawning from the Gear tab, is how rare item drops work.

In the right column, you can add what item the NPC tans for, if any, and the skill required to do the tan. You can also modify the drop pool, used for some boss NPCs like Saraxa. The drop pool is guaranteed to drop between min and max items, and it will pick that many items from the item list below it.

### Triggers

![](https://i.imgur.com/zPSGa8x.png)

In the left column, you can add "combat messages" for the NPC to randomly say during combat.

In the right column, you can create sound effects for certain triggers for the NPC. The two supported triggers currently are spawning and leashing (when the NPC goes back to its spawner).

### Faction Reputation & Summonability

![](https://i.imgur.com/U0WPiXB.png)

In the left column, you can see the faction outlook for this NPC. This determines if they're friendly or not with other factions. This can be easily set by hitting the red/green buttons.

In the second column, you can set how much faction reputation you get for killing this NPC.

In the third column, you can add stat scaling for summoning this creature (used only by creatures that are summoned by spells).

In the fourth column, you can add skill scaling for summoning this creature (used only by creatures that are summoned by spells).
