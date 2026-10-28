---
title: Jounral 9 - Skill Progression
description: Progression in the game has been a big question and debate, so we spent this week building quick prototypes to put them to the test.
date: 2026-10-27
---
# Goals/Tasks

We're at the point in development where we need to give players more mid- and long-term goals and encourage replaying the game, so we discussed skill and upgrade progression at length. Being unable to agree on whether mid-run or meta progression would be best, Dr. Faas suggested we build quick prototypes to test, so I spent the week building a skill tree system to use as meta progression.

## Skill Tree

Implementing this task was much more difficult than I anticipated. There are so many parts that go into a skill tree, and it wasn't until I started to build the system that I realized how much would need to change about our current build of the game to implement this meta progression. 

To start, I made a [`SkillComponent`](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/694d331a5c613fc7eae99bb2771f570ff773dfc3) that could be set up for each skill/upgrade on the tree. The `SkillComponent` takes in a name for its upgrade and an upgrade icon. The name of the upgrade will later be used to apply the upgrade to the player that selected it. Each skill can be locked, unlocked, and activated, and it can be [locked](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/fa92afcb72653fcda173fabbaa5ddf71ef05c5ea) by certain other skills. The component checks for GUI input, which allows it to act similarly to a button.

Then, I set up a [basic skeleton](https://github.com/KxtR-27/CS414_VipWaveSurvival/commit/17152f83e46df0c0e5e9dd76de48f15bc118a1c7) for the skill tree. I tried to make a more robust system from the start by setting up resources to aid in creating each skill tree, but I was having difficulty using them in a helpful way. I then decided to scrap the resources and instead made each character's skill tree from scratch (I just have a mockup for the wizard tree, with all the other trees just being a copy of the wizard one for now). With the help of setting up a `GlobalPlayerManager`, I was able to get the upgrade screen together such that the number and type of the skill trees is reflective of the number and character class of players in the game.

# Estimated v.s Actual Time

The work on the skill tree(s) took over 8 hours, which surprised me, especially since I wasn't even able to finish the system. I expected to be done with the whole system and its set-up after 8 hours, not to be about halfway, if even that much, done with it.

# Communication

I have been getting back into being as communicative as I can be this past week. I asked for help at one point, but unfortunately no one on my team responded to the request. I should have followed up, but time unfortunately got away from me, so I did not get the help I needed, although there were some things I was able to figure out on my own in the end.