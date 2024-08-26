---
title: "ModKit: NPC Scripts"
permalink: /docs/modkit-npcscripts/
---

## NPC Scripts

When making an NPC Script, there are a few tabs, although two of them will eventually be updated to support a friendlier UX for users. All the same:

### Core Stats

![](https://i.imgur.com/d9XQRPR.png)

The most important thing here to set is the Map NPC Tag, which determines which NPC to bind this script to on the map. Everything else set here is handled the same as in the NPC editor.

### Behaviors

![](https://i.imgur.com/dYeQM7r.png)

Here, you have to write YAML for your NPC behaviors. The most common NPC behaviors will be shops, but there are examples for everything! Check [here](https://github.com/LandOfTheRair/LandOfTheRair/tree/master/server/src/models/world/ai/behaviors) for a listing of behaviors, and you can find examples by checking the base content.

### Dialog

![](https://i.imgur.com/2XwfzDk.png)

Here, you have to write YAML for your NPC dialogs. This can be as detailed as you would like, but should be copy-pastable from other examples found in the base content. When in doubt, ask!
