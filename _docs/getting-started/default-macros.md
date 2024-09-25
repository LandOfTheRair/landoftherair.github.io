---
title: Default Macros
permalink: /docs/default-macros/
---

The game has a lot of internal macros that you might make use of while building your own custom macros. 

Any time you see `<target>` that means you can use a `targetish` when using the macro. A `targetish` is something that will identify the creature. It can be either the UUID (this is what the UI uses), or a part of the creatures name. So, if you have a creature named `Adacen`, you could use either `a`, `ada`, or `adacen` (or many others). The more specific you are, the better chance you have of not targetting something with a similar name on your screen.

**Beware**: Macros will not work when:

* The bank window is open
* The command line window is active
* Any modal is open (options, macro group editor, macro editor, etc)

# Macros

## Default Macros

These are macros built into the game, some added to your default hotbar.

If a macro says that it "supports instant use", that means you can pre-pend a `~` to make the macro happen instantly, for example: `use` will use an item in a round, but `~use` will use the item instantly.

Macro | Syntax | Description
----- | ------ | -----------
`chase`               | `chase <target>` | Move towards the target.
`climb up`            | | Climb up at the current location.
`climb down`          | | Climb down at the current location.
`up`                  | | Use the stairs at the current location.
`down`                | | Use the stairs at the current location.
`face`                | `face <dir>` | Face N, E, S, or W.
`empty`               | `empty <left|right>` | Empty the bottle in your chosen hand.
`fill`                | `fill <left|right>` | Fill the bottle in your chosen hand based on where you are.
`consider`            | `consider <target>` | Get a description of the target.
`trade enable`        | `trade enable` | Turn on trading. This will let you drag & drop items onto other players, and them onto you.
`look`                | `look` | Look at the ground, not searching anything.
`look`                | `look <dir>` | Look in a direction, examining the specifics of that object. Doors will tell you required key descriptions, etc.
`open`                | `open <dir>` | Open the door either N, S, E, or W from you.
`close`               | `close <dir>` | Close the door either N, S, E, or W from you.
`pettarget`           | `pettarget <creatureish>` | Force your pets to target a creature matching `creatureish`. If nothing is specified or found, agro will be reset. _Note_: Resetting agro doesn't mean your pet won't go after something. If the target still has agro towards the pet, the pet will go after it. You'll need to redirect agro to something else.
`write`               | `write <message>` | While holding an ink pot and an empty scroll, you can add your own message to the scroll.
`show stats`          | `show stats <all|leader>` | Get a listing of all or some of your stats. `show stats all` will give you everything, whereas `show stats` will give you the basics. `show stats leader` will show you your current leaderboard stats.
`show skills`         | | Get a listing of all of your skills.
`restore`             | | Revive yourself when you're dead.
`break`               | `break <hand>` | Break the item in your left or right hand. Permanent, irreversible, and only works if the item is yours.
`cast`                | `cast <spell>` | Cast `spell`.
`use`                 | `use <hand>` | Use the item in `hand`. Supports instant use.
`wield`               | `wield <slotNumber|itemType>` | Take an item from your belt and put it in the first available hand. Supports instant use.
`sheathe`             | `sheathe <left|right>` | Put the item in your left or right hand into your belt. Supports instant use.
`take`                | `take <itemClass|itemName> <from sack|belt|pouch|ground>` | Take an item that matches itemClass or itemName from the specified container and put it into the first available hand.
`place`               | `place <itemClass|itemName> <in sack|belt|pouch|ground>` | Take an item that matches itemClass or itemName from either the right or left hand and put it into the specified container.
`wait`                | | Do nothing for a tick.
`.`                   | | Repeat the last command.

## Emotes

You can emote at a target, or not. You'll see a different message depending on what you do. Some emotes will make you friendly towards the target, and some emotes will make you hostile.

A list of emotes is as follows:

* `agree`
* `dance` (friendly)
* `disagree`
* `hail`
* `hug` (friendly)
* `greet`
* `kiss` (friendly)
* `laugh` (friendly)
* `mock` (hostile)
* `prod`
* `scratch` (hostile)
* `scream` (hostile)
* `sing` (friendly)
* `spit` (hostile)
* `tickle` (friendly)
* `wave`

## Internal Macros

Macro | Syntax | Description
----- | ------ | -----------
`~drink`        | | Drink from your potion slot.
`~move`         | `~move <x> <y>` | Move X tiles and Y tiles.
`~search`       | | Search the corpses on the ground.
`~look`         | | Look at the ground, not searching the corpses.

## Class Skill Macros

Some classes get skills that are enhanced by their class, but are usable by other classes. Namely thief.

Macro | Syntax | Description
----- | ------ | -----------
`hide`      | | Hide in a nearby shadow. Exercises thief skill.
`steal`     | `steal <target>` | Attempt to steal from the target. Exercises thief skill. 
`backstab`  | `backstab <target>` | Attempt to backstab the target (charge + attack). Exercises thief skill.
`mug`       | `mug <target>` | Attempt to mug the target (charge + steal + attack). Exercises thief skill.
`set`       | `set <dir>`    | Set the trap you're holding in your right hand. Exercises thief skill.
`disarm`    | `disarm <dir>` | Attempt to disarm a trap. Exercises thief skill.

## Party Macros

Party macros are used when interacting with a party.

Macro | Syntax | Description
----- | ------ | -----------
`party create`      | `party create <partyname>` | Create a party with the name partyname.
`party join`        | `party join <partyname>`   | Join a party named partyname (requires leader to be visible).
`party leave`       | | Leave your party.
`party kick`        | `party kick <target>`      | Kick target from the party. Must be leader.
`party give`        | `party give <target>`      | Give the party leadership to target. Must be the leader.

## UI Interaction Macros

UI interaction macros come in a lot of forms, mostly they're for moving things around, like belt to sack, equipment to ground, etc. There are a lot of them, including these commonly used ones:

Macro | Syntax | Description
----- | ------ | -----------
`~BtR` | `~BtR <slot>` | Move item from belt slot to right hand.
`~BtL` | `~BtL <slot>` | Move item from belt slot to left hand.
`~BtS` | `~BtS <slot>` | Move item from belt slot to sack.
`~BtG` | `~BtS <slot>` | Move item from belt slot to ground.
`~StR` | `~StR <slot>` | Move item from sack slot to right hand.
`~StL` | `~StL <slot>` | Move item from sack slot to left hand.
`~StB` | `~StS <slot>` | Move item from sack slot to belt.
`~StG` | `~StS <slot>` | Move item from sack slot to ground.
`~LtG` | `~LtG` | Move item from left hand to ground.
`~LtS` | `~LtS` | Move item from left hand to sack.
`~LtB` | `~LtB` | Move item from left hand to belt.
`~LtR` | `~LtR` | Move item from left hand to right hand.
`~RtG` | `~RtG` | Move item from right hand to ground.
`~RtS` | `~RtS` | Move item from right hand to sack.
`~RtB` | `~RtB` | Move item from right hand to belt.
`~RtR` | `~RtR` | Move item from right hand to left hand.

## Advanced Macro Substitutions

Macro substitutions can be used to find creatures that meet a certain criteria for macro targetting. For example, healing the weakest player, or attacking the farthest NPC (potentially a runner). These can be used in any macro that targets a creature, such as with `chase $farthest` or `cast magicmissile $randomnpc`.

Here is a full listing of each substitution:

Substitution | Description
------------ | -----------
`$firstnpc`         | Replace with the first possible NPC.
`$firstplayer`      | Replace with the first possible player (excluding yourself).
`$first`            | Replace with the first possible creature.
`$randomnpc`        | Replace with a random NPC.
`$randomplayer`     | Replace with a random player.
`$random`           | Replace with a random creature.
`$strongestnpc`     | Replace with the strongest NPC (by HP).
`$strongestplayer`  | Replace with the strongest player (by HP).
`$strongest`        | Replace with the strongest creature (by HP).
`$weakestnpc`       | Replace with the weakest NPC (by HP).
`$weakestplayer`    | Replace with the weakest player (by HP).
`$weakest`          | Replace with the weakest creature (by HP).
`$farthestnpc`      | Replace with the farthest away NPC.
`$farthestplayer`   | Replace with the farthest away player.
`$farthest`         | Replace with the farthest away creature.
`$closestnpc`       | Replace with the closest NPC.
`$closestplayer`    | Replace with the closest player.
`$closest`          | Replace with the closest creature.

# Suggested Macros

There are a lot of interesting combinations you can work with while making macros in Land of the Rair. Some of my favorites are these:

* `~LtG; steal` (drop left item on ground, then steal)
* `~LtG; mug` (drop left item on ground, then mug)
* `take bottle from sack` (take a bottle from sack)
* `take heal from sack` (take an item with "heal" in the name, from sack)
* `take bottle;use right;place bottle` (take the first bottle from your sack, use it, then put it away)
* `cast heal $weakestplayer` (cast heal at the weakest player)
