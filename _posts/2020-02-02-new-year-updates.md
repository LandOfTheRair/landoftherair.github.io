---
layout: post
title:  "Land of the Rair Dev Blog #4"
date:   2020-02-02 12:00:00
author: Seiyria
---

These past few months have been a bit slow, admittedly rewriting a gigantic game with 70k+ lines of code is a bit difficult at times. I have been working on it a bit over the last few months, though! A lot of changes involve some internal re-structuring and re-architecting of how the code works. That took a fair amount of time to research and implement on its own!

However, I do have some relevant information regarding gameplay modifications / where I am. Last week, I've made it so you can actually move around in the world again! It was quite an undertaking (surprisingly). I'm still working through all of the content in the tutorial and making it work again, so I hope to be talking about npcs, monster AI, shops, and the like soon!

This has also come with a gameplay change that will change a bit how players play, but ideally not too much. Previously, movement actions and other UI related actions were instantaneous. It was nice, but it caused a lot of problems, especially with macros. Now, all macros can be made "slow" (ie, not instant) so they can be done sequentially. But, also, there are now two game loops - a fast one and a slow one. The fast loop operates on a 200ms loop, and the slow loop operates on a 2000ms loop. I've gotten feedback that the previous gameplay loop was a bit fast, so I'm going to slow it down by 100%. The fast game loop now will handle all "fast" actions which includes movement and UI updates for now. There is still room for instantaneous actions where necessary, but I don't know what that will include at this time.

Another improvement is to internal game speed/processing. Previously, I had to get all data on the client from the server about every item, every npc. Now, I will be embedding all of the item and npc data in the client to improve access speed. This will ideally also help out with the ground item processing (of which I have more planned changes to make too).

I am also working on new tools for players to create content for the game. I'd like to talk more about those at a later date, but for now, I'll be moving guides and creating more and putting them on the website. The first guide I've moved over was the [old map making guide](https://rair.land/docs/map-making/). It will need some updates when the mod tools are in a better state, but for now, you at least don't have to dive on the old Rair wiki to find it.

That's all for now!

- Seiyria
