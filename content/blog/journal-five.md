---
title: Journal 5 - End of Milestone 1
description: Mostly polish of user interaction with UI, plus implementation of game pausing.
date: 2026-09-28
---
# Goals/Tasks

My docket for the week was a little smaller than past weeks. Technically, I worked on local multiplayer at the start of the week, but I counted that towards my last journal, so I won't mention that again here. Otherwise, I mostly focused on fixing up UI element navigation and making sure most of the important menu screens were built. I was also supposed to start implementing control/input hints to signal to the player which button or key to press, but I didn't get far with that.

## UI Element Navigation

Thankfully, it was pretty simple to implement the joypad menu navigation because Godot has a built in `Focus` property on `Control` nodes. Most `Control` nodes allow you to call `grab_focus` on them, which allows you to select that node as "focused" when the scene loads. When a node is "focused," it has a thin and bright outline around it to indicate to the user that the node is being focused on. Right now, the focus automatically appears in the menu, regardless of if there is a keyboard and mouse connected or a joypad, so I might switch it so that it only appears for joypad. I would also like to add this focusing mechanism to the character select screen/component, however, the `Control` nodes in the component scene were giving me trouble that may have something to do with how the component is added to the character select screen. [Here](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/8b2032ee3d873ec61af147d34078b8ebae6e367e) is the overall work on the UI navigation.

## Pausing Game Time

I had to figure out how to pause game time for both the [debuff selection pop-up](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/34ccc9f202c9640642603d85d8bf288b8087bf5b) and a [game menu pause screen](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/133bad608d5a37512f3c287ca5c364dd65a857bc). Godot also makes this fairly easy, as there is a `get_tree().paused` call that can be made which pauses all elements that have their `process_mode` set to "Pausable" or "Inherit" (if the node is a child of a pausable node). All I had to do then was set the pause menu's `process_mode` to "Always" (although I need to go back and check if "When Paused" is better for a pause menu).

## Control Hints

I didn't end up finishing the control hints feature because there were some file type errors that were fighting me on implementation. I did find a Godot Add-on in the Godot Asset Store that does this for you, but I didn't get a chance to look closely enough at it to put it to use, so I might have to revisit it at some point.

# Estimated v.s. Actual Time

My estimated time this week was much closer to my actual time than usual, mostly because I had somewhat easier tasks to accomplish for the week. The only part that took longer was the control hints feature, but that one was slightly lower priority on our tasks list, so I can afford to wait and do it another week (probably this next week).

# Communication

Our communication as a group continues to be good, and we were able to easily hash out an issue we had in the last week that resulted from a miscommunication. I look forward to continued collaboration with my group.