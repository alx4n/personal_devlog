---
title: Journal 8 - Bugs and Refactoring
description: I worked a lot on our character selection menu, both fixing bugs and reorking our current system.
date: 2026-10-20
---
# Goals/Tasks

I spent the week fixing several bugs and general issues related to the character selection menu.

## Bugs

One of the bugs we had encountered in the playtest was that you could "change" your character in the character selection menu after confirming your selection, but it would only change within that menu, not within the actual game. Part of the issue was that we were disabling the arrow buttons after the character was confirmed, but this didn't seem to disable the shortcuts (and I think we were accidentally bypassing the buttons, but that's a separate issue). To fix this, I just needed to check if the buttons were disabled in one of the conditional checks that switched the character icon, which I fixed in [this commit](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/71d474a7bb7a23018886734254cb83f6b5930e0b).

Another bug we had encountered was that any new players that joined after all the other players had confirmed their characcters wouldn't be added to the main game. This was a little trickier to find the culprit of this bug, but it turned out we hadn't checked for the case that the number of connected players increases compared to the ready players, and we also had some redundant arrays that made things unnecessarily confusing, so I [consolidated arrays and implemented that condition check](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/910a99cf4ebe933d819beffc34993841e82d1be1).

## Refactoring

The initial way we had set up the `CharacterSelectScreen` made it so that technically infinite players could join the game, but they would also clip off the screen if they were the 5th player and onward due to how the container was set up. Instead, our team discussed refactoring the menu so that a maximum of 4 players could join. We also discussed refactoring in a way that all the player slots were visible from the start, so that they became enabled when a player joined instead of populating the container. This took some work because it required restructuring a lot of the code in the `CharacterSelectScreen`, although there was also a lot of code that could be reused after being tweaked.

As an indicator of the enabled/disabled condition on each slot (`CharacterSelectComponent`), I messed around with several methods of graying out the box. In the end, I used a `TextureRect` of the same background image as used for the slot, changed its color to fully black, and lowered the opacity to overlay it. I also toggled the visibility of the arrows depending on whether a player had joined. Then, I needed to connect a signal from the `CharacterSelectScreen` to the `CharacterSelectComponent`'s so that each component knew when its player joined and it could become enabled. I might rework this slightly so that there is actually a "enabled" signal or boolean instead of seemingly artibitrarily changing each of the elements to change the appearance of the component, although that might be unnecessary, since those things all occur in response to a signal from the menu. Either way, [here](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/962818935ff75a2807ae02cc7679098015fd92cc) is the commit that covers all of the above.

# Estimated v.s. Actual Time

I ended up surprised at how quickly I was able to resolve some of the bugs, I knew they wouldn't be too difficult but I expected more work there regardless. In contrast, I expected the refactoring of the character select menu to take less time than it did, although there might still be some work to be done depending on input from my teammates.

# Communication

Xander and I were able to get a lot of brainstorming done over the course of the week, so we made a lot of progress in discussing future goals and whether we need to revisit design pillars. Unfortunately, Kat wasn't able to join us for these discussions, but I caught her up as much as I could over Discord.