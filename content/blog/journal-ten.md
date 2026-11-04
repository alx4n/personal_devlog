---
title: Journal 10 - Health Refactoring and Respawns
description: Trying to implement respawning proved harder than expected.
date: 2026-11-03
---
# Goals/Tasks

After discovering a new bug, I discussed player respawns with Kat as a work-around to the bug. We had wanted to implement player respawns from the start, so this was a good time to work on a feature long overdue. Besides that, I fiddled some more with the skill trees, although I didn't make much progress in that regard.

## Respawns

In theory, respawns should have been easy, and for the most part, they were. What made everything much more difficult was that our health systems weren't working correctly in the way the stats were being updated and the way everything connected to the HUD. I spent 3-4 hours just trying to figure out why the stats were wrong and the HUD wasn't matching the player's actual stats. Eventually, I was able to fix it so that everything updates properly, but it took a lot of digging through different files to find where everything was being referenced. I wasn't able to split up the commit with all those fixes plus the respawns and deaths very well, so [here's](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/1387e1689cbe4b063e32ae8e6cfdab03fdfff9d1) the commit that encompasses all of that work.

## Skill Trees and Saving

I don't have anything to show for this, since I didn't make much tangible progress on the skill trees and saving and loading. However, I did start to work on the saving system, and that mostly required combing through the work that we have to figure out what needs to be saved and how.

# Estimated v.s. Actual Time

Debugging the health system took a frustrating and surprising amount of time. Combing through our work, both for the health systems and stats and skill upgrades, took a lot more time than I expected it to.

# Communication

Communication is going well with the group, although we're still having some disagreements over progression implementation, which we've established that we'll probably only be able to finalize after playtesting.

# Gold Stars

Kat did a lot of work on optimizing the skill tree set-up so that we can use recursive resources to set up skill trees. She did this fully based on my poor description of what I wanted to implement to help with that set-up.