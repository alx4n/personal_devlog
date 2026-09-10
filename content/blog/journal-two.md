---
title: Journal 2 - Project Beginnings
description: This post describes work I completed in the first week of development.
date: 2026-09-09
---
# Goals/Tasks

This week, my main goal was to get a working enemy NPC that had a way to zone in on targets. My secondary goal ended up being to implement a scalable and reusable damage and health system.

## Base Enemy NPC

First, I implemented a basic code structure that checked whether a target existed and if it did, the enemy would move in the direction of the target. This can be seen in my [Initial barebones implementation](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/e502de5e538629dfdf4a2e5d05eb0e57308e27b8). 

After I had that implemented, I attempted to create a state machine. The idea behind it was that enemies would automatically walk towards the center of the arena in a "locating" state, and upon an eligible target entering their targetting area, the enemy would switch to the "targetting" state and follow that target. Here is the [state machine implementation](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/de9171b850ddcef036e2fdb73278fc40d6127cd8). It may not have been the best solution, but it felt reasonable for a first draft. In the end, my code ended up being completely refactored by another team member, whose solution I like better as it feels more scalable than mine was.

## Health and Damage Components

My second task for the week ended up being to implement damage and health component systems to make health tracking easier across characters, both playable and non-playable. To do this, I adapted a previous health component system I had created last semester for the old game I had worked on in pre-production. Here is the [implementation of the two components](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/a868123107f8d07d9b20431d9f14ec122e3c5c43).

Something I did differently in this implementation of the health component compared to prior attempts at this component was that I made it a control node scene that automatically holds a progress (health) bar. This way, there is no need more many signal connections that have to be set up for each individual character. However, this only works when assuming that every character's health bar is displayed and looks the same way. So this may need to be changed as we progress in production.

In theory, this component system should make it easy to grant damage-dealing capabilities to characters (in the case of the damage component) as well as track or adjust health (using the health component). I'm curious to see how this system will improve as the game expands, and whether it will end up being as useful as it seems at the moment. It is entirely possible that it will be completely refactored or scrapped before the end of production.

# Estimated v.s. Actual Time

I am admittedly somewhat rusty from the summer, in which I had to divert my focus from game development and programming as a whole for more pressing tasks. As a result, my actual time spent on each of these tasks was far more than I had estimated. I was planning on having perhaps one more feature done for this week, but that ended up being less feasible than I expected.

# Errors and Struggles

My main struggle for the week was wrapping my head around the architecture I wanted to implement and translating my ideas into code and systems. Like I mentioned before, I'm still brushing off the dust on my game development skills, and getting in the mindset of creating systems is one of my biggest struggles when jumping headfirst back into a project such as this.