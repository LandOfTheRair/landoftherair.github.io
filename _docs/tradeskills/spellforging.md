---
title: Spellforging
permalink: /docs/spellforging/
---

Spellforging is a tradeskill in Land of the Rair, defined by it's ability to disenchant items, enchant items, and attach runes to items. To do spellforging, find any spellforger - for example, Zarn in the Steffen Homlet town. You must have a conjuration skill of 1 or more to spellforge.

To disenchant an item, just place any valid equipment item on the left-most side and hit disenchant. This will give you Enos and Owts dust, based on the quality of the item. The higher quality the item, the more likely you are to get Owts dust. You will always get Enos dust.

When you get to 100 dust, you can make an Enchantment Brick. You can use these in combination with any item to enchant them, increasing either their offense and defense, or their damage output. If you enchant using an Enos brick, it will increase the offense and defense of the item by 1. If you enchant using an Owts brick, it will increase the item tier, which adds bonus damage rolls to the item. Items are hard-capped at +5, and every few skills (counting both spellforging and conjuration) your success chance will increase.

You can also attach traits to equipment using rune scrolls. These are semi-rare. An item can have a maximum of one trait on it at any time, and attaching a new one will overwrite the old one. Your success chance increases only with your spellforging skill.

If you happen to come across a Runewritten Scroll (created by [Healers doing Runewriting](https://rair.land/docs/runewriting/)), you can use their scrolls and attach them to ammunition-class items, such as arrows. This will impart the spell upon the ammunition item. 

### Useful Macros

* Disenchant: `~StT 0 spellforging 0 $spellforging; disenchant $spellforging` - put the item from the first sack slot (bottom right) into the disenchant slot, then disenchant it
* Enchant: `~RtT spellforging 0 $spellforging;~StT 0 spellforging 1 $spellforging;enchant $spellforging;~TtR spellforging 2 $spellforging` - move item in right hand into enchant item slot, move scroll from bottom of sack into reagent, enchant, then move the item back into the right hand
