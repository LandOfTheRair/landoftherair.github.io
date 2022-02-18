---
title: Map Making
permalink: /docs/map-making/
---

## Tiled Settings

You should change these settings to ON, or you're going to have a bad time:

* View -> Snapping -> Snap to Grid

## Creating a Map

When creating a map, it should follow these constraints:

### Map Structure

There **must** be a gutter (margin) of 4 tiles on each edge of the map (see any map for an example). Otherwise, the camera will get messed up.

### Map Layers

Each map should have these map layers (in order; if you copy a map, they will be):

1. ZLevel - this is an object layer that uses *only* rectangle objects. It's used to specify what's above or below what on the map.
1. SpawnerZones - this is a legacy layer, don't use it for anything.
1. Succorport - this is an object layer that uses *only* rectangle objects. The rectangle object name sets the region name in succor/teleport.
1. BackgroundMusic - this is an object layer that uses *only* rectangle objects. The rectangle object name sets the BGM played in the region.
1. RegionDescriptions - this is an object layer that uses *only* rectangle objects. The rectangle objects set the description for the area contained inside of it. Additionally, if there is no succorport, any succor/teleports will use the name of this RegionDescription.
1. Spawners - this is an object layer specifically for spawners. Generally, they are restricted to the pylon sprite to prevent confusion.
1. NPCs - this is an object layer for specific scripted NPCs. This typically includes shops, quest givers, and the like.
1. Interactables - this is an object layer for anything interactable - doors, stairs, portals, or map event tiles.
1. OpaqueDecor - this is an object layer for decorative things that should not be see-through-able but can be walked through. Typically, secret walls are put on this layer.
1. DenseDecor - this is an object layer for decorative things that should also not be walk-through-able (but can be seen through). Typically, counters are put on this layer.
1. Decor - this is an object layer for decorative things such as beds, barrels, etc.
1. Walls - this is a layer specifically for walls. Sparingly, trees may also be placed here to make them opaque/dense.
1. Foliage - this is a layer specifically for trees and plants.
1. Fluids - this is a layer for water and lava only. Do not put anything else (ie, pools, fountains) on this layer.
1. Floors - this is another visual layer on top of terrain, it has no effect other than affecting visual tile layering. Typically carpets, bone piles, etc will go on this layer.
1. Terrain - this is the base layer and is the tile that is the general basis of your map - grass, dirt, tile, etc.

### Optional Properties

Maps have optional properties that can be set:

* `maxCreatures` (Controls the maximum number of creatures on the map. When set to 0, spawners will only spawn their minimal number. default: 1)
* `maxSkill` (Controls the max skill you can gain skill points at for this map. default: 1)
* `maxLevel` (Controls the max level you can gain xp at for this map. default: 1)
* `region` (Controls the region this map belongs to. Affects banks, lockers, regional drop tables)
* `itemExpirationHours` (Controls how many hours it takes for items to decay on this map. default: 6)
* `itemGarbageCollection` (Controls how many minutes it takes for item garbage collection checks to occur. default: 60)
* `maxItemsOnGround` (Controls the max items on ground before decay is forced to start. default: 1000)
* `subscriberOnly` (If set to true, non subscribers cannot enter the map)

### Additional Objects
For some specific objects, there is additional configuration required:

#### Secret Walls
These must be on the "OpaqueDecor" layer, and must have the type "SecretWall".

#### Event Sources
Event Sources can be added to fire events when entering or exiting a tile. They can have these properties:

* `offEvent` - the event name fired when leaving
* `onEvent` - the event name fired when entering

#### Lockers
* `name` needs to be set to the locker name. 
* `type` needs to be set to Locker.
* `lockerId` needs to be set to a unique id (or non-unique, to share a locker with a previous area)

#### Stairs, Holes, Teleport Tiles
* `type` should be set to StairsUp or StairsDown or Teleport or ClimbUp or ClimbDown or Fall
* `teleportMap` should be set to the map to teleport to
* `teleportX` should be set to the x position on the map to teleport to
* `teleportY` should be set to the y position on the map to teleport to
* `requireHeld` can be set to an item name if it's needed to get through.
* `requireQuest` can be set to require a quest be started for a player (always true if the quest is completed)
* `requireQuestProgress` can be set to require a key in the quest data be true (always true if the quest is completed)
* `requireQuestComplete` can be set to require a quest be complete for a player
* `damagePercent` can be set to a number 0..100 if the `type` is Fall.

#### Doors
* `type` should be set to Door
* `requireHeld` can be set to an item name if it's needed to get through.
* `requireLockpick` can be set to true or false if the door can optionally be picked (required if no requireHeld is set)
* `skillRequired` can be set to the thief skill required to be able to use the lockpick (Thieves only)
* `requireEventToOpen` can be set to make it so the door only opens in response to events
* `lockedIfAlive` can be set to a mob name to make it so the door only opens if no mobs matching the id given are alive

#### Drinkable Areas
* `type` should be set to `Fillable`
* `fillEffect` should reference an effect that exists
* `fillDesc` should be a description of the liquid

#### Spawners
* `randomWalkRadius` is the number of tiles in any direction from the spawner the creature will naturally walk (default: 10)
* `leashRadius` is the number of tiles in any direction from the spawner the creature will chase a hostile target (default: 20)
* `respawnRate` is the number of ticks (half-seconds) it takes for a creature to spawn from this spawner (default: 240)
* `initialSpawn` is the number of creatures spawned immediately when the 
* `script` set to the script for the spawner. For lairs, it should be set to `global/lair`.
* `lairName` set to the name of the lair creature to spawn (optional: for lairs only)

#### Alchemist
* `script` should be set to `global/alchemist`
* `alchCost` is the cost to combine ounces of a potion
* `alchOz` is the maximum number of ounces the alchemist will combine to

#### Smith
* `script` should be set to `global/smith`
* `costPerThousand` is the cost per thousand of condition (avg=20000) to repair an item (default: 1)
* `repairsUpToCondition` is the max condition the smith will repair to (default: 20000)

#### Tanner
* `script` should be set to `global/tanner`

#### Peddler
* `script` should be set to `global/peddler`
* `peddleCost` should be set to a cost in gold to buy an item
* `peddleItem` should be set to an item name

#### Banker
* `script` should be set to `global/banker`
* `bankId` should be set to the region the bank is in
* `branchId` should be set to the branch the bank is (flavor text, usually set to the town name)

#### Other NPCs
* `script` should be set to their script.

## Making a Map More Easily

* Use the terrain brush to place water, carpets, tiles, floors, etc. It will automatically place edges for you. Hold CTRL to make it place a 2x2 instead of 3x3. To place a 1-wide, you'll have to do that manually.
* To place trees, use the random (dice) button. Ctrl-select multiple trees, then place them using the brush. This will help avoid an unnatural-feeling forested area.

## Map Guidelines

These are in no particular order, but in order to make it easier on both of us. When in doubt, ask, or check an existing map to see how it is done there.

* Maps need 4 buffer tiles on each of the edges. The first tile you can place is at 4,4.
* Do not make maps greater than 200x200. You do not have the patience nor the time to fill it properly with the details, especially if it is your first map. Start small, expand if you need to. Also, large maps do not work well within the game engine - 250x250 (Frostlands) is the largest map currently, and while I would like to push the boundaries, it requires testing.
* When placing walls, do not transition directly from one wall into another (ie, gray cave to gold cave).
* Do not use too many terrain/wall tiles in an area. If you have more than 3 unique walls in your zone, you probably are using too many. Consistency is key.
* Use decor. If you don't have any decoration, your map will feel empty.
* Remember, the player viewport is a 7x7 field of view. Do not make areas too large or plain, or they'll be unremarkable.
* When making cave areas, or areas in caves, try to make the cave look more natural (do not make a giant flat wall the whole way).
* Do not use "shiny" rugs. Maybe some day, but not today.
* Do not put anything on the spawner or NPC layer. I will have to remove them and edit them to make them work.
* Make all of your teleports work correctly.
* Do not "hide" things in general (such as invisible traps). Players should not be blindsided by things in an unpredictable manner.
* Only put counters on DenseDecor.
* Only put secret walls on OpaqueDecor.
* Do not place interactables that are not valid. See above for valid interactables. Most of them will be doors or teleports.
* Please put RegionDescriptions on your map, and spell check them. I will do a final review of them. If you're curious how to do that, pull one from another map via copy/paste.
* You can put BGM if you want to. Copy and paste from another map if you're unsure how it works.
* The Succorport layer is only necessary if you want to restrict succor/teleport in a particular zone. Usually, this is used for lairs or progression areas to prevent skipping.
* The ZLevel layer is only necessary if you have areas in your map that are above/below others.
