---
title: "ModKit: Recipes"
permalink: /docs/modkit-recipes/
---

## Recipes

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
