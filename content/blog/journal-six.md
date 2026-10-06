---
title: Journal 6 - Control Hints and Playtest Reflection
description: Had some struggles with implementing dynamic control hints which led to a simpler solution. Had a very revealing playtest on Friday. 
date: 2026-10-06
---
# Goals/Tasks

My main priority for the week was to help players understand controls by implementing a control hint system.

## Control Hints/Controls Menu

I really wanted to dynamically suggest controls to players depending on their connected controller, so I initially spent a lot of time trying to figure out a way to do so, again to a lack of many resources on the subject. I did find a Godot Add-on that was available in the Godot Asset store called [Controller Icons](https://store.godotengine.org/asset/rsubtil/controller-icons/), however I was struggling to figure out how to use it because the documentation wasn't the best, so I ended up discarding the add-on, although I might try to revisit it later. 

In the end, in place of a dynamic control hint system like I envisioned, I decided to simply create a control menu scene that was linked to from the main menu. This was a last minute implementation, right before the Friday playtest, but once I fleshed out the [keyboard controls display](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/c282e7653f8c42033fe8ce3f888423cc973c50ff), I got help from my teammate Xander to work on the [gamepad controls](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/b25bb37189ec1d36634aec686b9eb0e7eb9ec650) while I wrote some simple logic to [toggle between the two](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/c1c91ede917c54837e3b62715d891b6ebae6ddd5). Thankfully, I was able to reuse some code from the `CharacterSelectComponent` for the schematic-switching logic.

## Revealing Playtest

Specifically in terms of controls, the playtest proved to be very revealing. The most interesting thing that I noticed was that almost everyone skipped the main menu button labeled "Controls" and tried to jump straight into the game, which meant they were often confused about what abilities they had and what each button or key did. In hindsight, that makes sense, since often games teach you the controls when you first begin. However, it surprised me in the moment, especially when someone would restart the game several times and continually ignore the "Controls" button. 

Clearly, we either need some sort of tutorial to begin the game or the controls and available actions need to be visible for players at all times. The latter option would likely cap our game to a maximum of 4 players, which doesn't rule it out but brings up the point of how many players we want to be able to play at once. Either way, the controls need to be much clearer to players. The controls menu will still be useful for players to reference, but it shouldn't be required reading to play the game.

We also got useful feedback about certain controls being different than expected by the player, so it will be useful to look into other games to see how similar controls are handled, that way our players won't feel like the controls they are learning are counterintuitive. 

# Estimated v.s. Actual Time

My estimated time and actual time spent on the controls were close, although not because I had accurately estimated the time, but rather because I spent a lot of time on one solution and then pivoted to a much faster and simpler solution in the end.

# Communication

I need to be more communicative with my team when I feel like I am falling behind in my work or running low on time. I didn't accomplish much this week because of lack of time, but that should have been communicated better to my team in case anyone else needed to pick up the slack to make sure we were still making progress and meeting deadlines.

On the other hand, Xander and I had a good exercise in communication when working together on the controls menu, which went really well. I was able to communicate my idea and what needed to be done, which led to effective collaboration.