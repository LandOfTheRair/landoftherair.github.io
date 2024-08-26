---
title: "ModKit: Get Started"
permalink: /docs/modkit/
---

## Getting Started

_Unfortunately, at this time, the ModKit is Windows only. You could build it on other platforms if desired, though._

1. [Download the Modkit from GitHub](https://github.com/LandOfTheRair/mod-toolkit-v2/releases/latest/download/LandOfTheRairModdingTools.zip).
1. Unzip the archive, and run `Land of the Rair ModKit.exe`.
1. When the ModKit opens, it will download a bunch of resources. This will cover some, but not all of the resources you will need. These are the essentials to get up and running, though.

Upon completion of these steps, you should see something like this:

![](https://i.imgur.com/RrGvzFx.png)

## Loading the Base Game Content

If you want to check the base game content out, make changes or tweaks, or test it, this section is important!

If you intend to _contribute fixes back_, you should set up and install [git](https://git-scm.com/), [clone this repository](https://github.com/LandOfTheRair/Content), and have a GitHub account.

If you _only_ want to test, you can download [this file](https://github.com/LandOfTheRair/Content/blob/master/mods/BaseGameContent.rairmod).

Either way, you will have a `BaseGameContent.rairmod` file available to you. From here, Go into the Actions menu and import the mod. You can follow the rest of this guide for usage or testing as normal.

It will automatically sync changes back to this file, which you can use to easily submit pull requests on GitHub, too!

### The Menu

![](https://i.imgur.com/wX17Q5p.png)

Most of this menu will be straightforward, but there are some important details to know about certain options. Only those options will be covered:

#### Mod Testing

When testing your mod (which you should!), you will first need to hit "Install MongoDB..." and "Install Rair Server..." to download and install the executable server code, as well as a database. The total download will be ~370mb (which is why it's not done at startup).

After this, you can Test Mod, which will let you actually get in there and test your maps, content, etc.

![](https://i.imgur.com/GbuoWHC.png)

On the left side, you can set the level, map, x/y to force upon all characters for really quick testing. On the right side, you could set "extra" properties if you knew the property you wanted to set. For example, you could set it so any time you log in, you are also the "GM" allegiance, which makes you neutral to all creatures. To do this, you would set the Extra Character Settings to: `{ "allegiance": "GM" }`.

If you have the open client option checked, it will open a new instance of the client pointing to your local server. You generally don't want to open more than one client as it will kick you out of the others.

You can also kill all database and server processes running, if for some reason they're lingering around.

Once you get into the game, you can use GM commands to tweak, summon, or otherwise test your mod. You can [find more information on that here](https://landoftherair.github.io/docs/gm-commands/).

#### Analyze

This will open the analysis tool, which lets you run various reports based on the content in the game. This will spit out analytic information to help inform content creation decisions.

![](https://i.imgur.com/shotC5q.png)

#### Pinpoint

This will open the pinpoint tool, which lets you look for all usages of a certain Thing in the game.

![](https://i.imgur.com/4RaSCvX.png)

#### Query

This will open the query tool, which lets you query the entire mod using SQL or JS, and generate custom information layouts based on that.

_Tip: Press Ctrl+S to run your current query_

_Note: If your query is too intensive, you might crash the mod tools :(_

##### JavaScript Notes

- [Lodash](https://lodash.com/docs/) is automatically injected into the page for query usage.

Example Query (will group all items by item class):

```js
function query(mod) {
  return _.groupBy(
    mod.items.map((i) => ({ itemClass: i.itemClass, name: i.name })),
    "itemClass"
  );
}
```

##### SQL Notes

- [AlaSQL](https://github.com/AlaSQL/alasql/wiki) is used to do iteration
- [ModKit.ts](https://github.com/LandOfTheRair/mod-toolkit-v2/blob/main/src/interfaces/modkit.ts) can show you the layout of the ModKit, although they're mapped differently - `npcs: INPCDefinition[]` becomes: `{ type: 'npc', data: ... }`
- When querying, you are _always_ querying from `?`. There are no tables. All items are in one "table".

Example Query (count all ModKit entries by type):

```sql
SELECT type, COUNT(type) AS totalCount FROM ? GROUP BY type;
```

Example Query (count all items and group them by itemClass):

```sql
SELECT
    data->itemClass AS itemClass,
    COUNT(data->itemClass) AS itemTotal
FROM ?
WHERE type="item"
GROUP BY data->itemClass;
```

Example Query (get all gems and pull out their name as itemName):

```sql
SEARCH
    /WHERE(type="item") AS @entry
    /WHERE(itemClass="Gem") AS @item
RETURN(@item->name as itemName)
FROM ?
```

![](https://i.imgur.com/soLiArf.png)

#### Update Autogenerated Content

This option creates lore scrolls and trait scrolls from existing lore and traits in the system. It should be run if there are new traits added, or if there are new gems added.

#### Update Resources

This option retrieves all spritesheets, template maps, and configuration data in the base Land of the Rair game (effects, spells, etc) for usage with the editor. If there are ever new spells that you would like to use in your mod, but don't have them, update resources to obtain them.

## FAQ

Here are some frequently asked questions that may have come up while reading this page.

### What is Weighting?

When there is a "weight", that means that all options in the list will be "weighted" against each other when picking from that list. If you have 3 entries with weights 1, 1, and 1 they are all equal weight, and all likely to be picked. However, if you have entries with weight 3 and 1, then the first entry is 3 times as likely to be picked.

In this editor, there is also the ability to specify -1 as a weight, which means "always" (in certain contexts). If there are ever two inputs (as with NPC drops, and NPC sack), the left one will be "chance" and the right one will be "max chance" - set chance to -1 to ensure it always appears or drops (max chance can be set to anything). Otherwise, it will be a chance / maxChance of appearing (usually, you would set chance to 1, and maxChance to something like 100 for a 1/100).

In some cases, it is preferred to not use the -1 notation, and instead have a "none" result (this is the case with all NPC equipment). It is possible that this will one day be made homogenous; but that is not how it exists today.

Sometimes, there is also a "max chance" option next to a weight, or the option itself functions as "max chance" instead of "weight". In this case, the option will not be weighted, but instead will drop in a 1/max chance.
