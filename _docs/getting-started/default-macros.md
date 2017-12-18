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

Macro | Syntax | Description
----- | ------ | -----------
`chase`               | `chase <target>` | Move towards the target.
`climb up`            | | Climb up at the current location.
`climb down`          | | Climb down at the current location.
`up`                  | | Use the stairs at the current location.
`down`                | | Use the stairs at the current location.
`look at`             | `look at <target>` | Get a description of the target.
`open`                | `open <dir>` | Open the door either N, S, E, or W from you.
`close`               | `close <dir>` | Close the door either N, S, E, or W from you.
`write`               | `write <message>` | While holding an ink pot and an empty scroll, you can add your own message to the scroll.
`show stats`          | | Get a listing of all of your stats.
`show skills`         | | Get a listing of all of your skills.
`restore`             | | Revive yourself when you're dead.
`.`                   | | Repeat the last command.

## Emotes

You can emote at a target, or not. You'll see a different message depending on what you do. Some emotes will make you friendly towards the target, and some emotes will make you hostile.

A list of emotes is as follows:

* `agree`
* `dance` (friendly)
* `disagree`
* `hug` (friendly)
* `kiss` (friendly)
* `mock` (hostile)
* `prod`
* `scratch` (hostile)
* `scream` (hostile)
* `sing` (friendly)
* `spit` (hostile)
* `tickle` (friendly)

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

UI interaction macros come in a lot of forms, mostly they're for moving things around, like belt to sack, equipment to ground, etc. There are a lot of them.

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

# Suggested Macros

There are a lot of interesting combinations you can work with while making macros in Land of the Rair. Some of my favorites are these:

* `~LTG; steal` (drop left item on ground, then steal)
* `~LTG; mug` (drop left item on ground, then mug)
