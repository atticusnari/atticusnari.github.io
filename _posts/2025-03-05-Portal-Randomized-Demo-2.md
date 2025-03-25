---
title: Portal Randomized Demo 2 Released!
date: 2025-03-05 12:00:00 -0500
categories: [Mod Development, Portal Randomized]
tags: [portal randomized, mod development, memesrus_124]     # TAG names should always be lowercase
description: Explore 2 additional supported chambers and 2 new effects!
published: true # Make true when publishing
media_subpath: '/assets/media/20250305-2'
image: Portal Randomized Demo 2 4.3.png
---

# Download on [ModDB](https://www.moddb.com/mods/portal-randomized/downloads/portal-randomized-demo-2)

## Mod Description

This demo contains the first two maps of Portal with all of the current random effects at this time:

- The Floor is Lava
- Water Flood
- Random Gravity
- Random Speed
- Zombie Spawn
- Turret Spawn
- Neurotoxin Escape
- Lights out
- Small Chell
- Combine Mini Assault

If you are updating, I highly recommend deleting Portal Randomized folder and adding new one.
Replacing files could give unexpected bugs or behaviors.

If you see any bugs or have any suggestions,
the easiest way is to comment on the [ModDB page](https://www.moddb.com/mods/portal-randomized)

## Changelogs (in order)

[UP TO DATE CHANGELOGS INCLUDING IMAGES FOR ADDITIONAL INFORMATION](https://docs.google.com/document/d/1xWkk2UfuSLpvoNInK5WddU3-MDtScrxAngO_9NHt8ao)

Added support for Test Chamber 02 and 03

Added Small Chell and Mini Combine Assault effects

Made Hardcore Mode choose 3 random effects instead, and made the old version into IMPOSSIBLE MODE (which triggers every effect at once, if you don’t already know)

Made it so when starting a new game, gravity it set to default just in case you left a map with sv_gravity set to an abnormal value, such as in hardcore mode (thank you lawlaw0 from ModDB)

Adjusted Lights out timing to make the time in the dark less (thank you Cake from Portal Mapping and Modding Discord)
5 seconds to 3 seconds

Extended trigger for Neurotoxin escape in Test Chamber 00 as it wouldn’t trigger if you didn’t exit the first portal. Preventing you sneaky speedrunners and making hardcore a little more hardcore :)

Fixed nodraw leaking into the real world where it doesn’t belong (good luck finding out where)

Added player clips to observation rooms so you cannot escape the fun

Made portals that need their height changed due to lava, only do so when Floor is Lava effect is applied (thanks to lawlaw0 from ModDB)

Renamed New Game options on the main menu to make it less confusing what you’re supposed to select. I would love to integrate a hardcore dialog menu but I haven’t [figured it out yet](https://www.reddit.com/r/SourceEngine/comments/1iud3mr/anyway_to_make_a_custom_dialog_box_like/)!

Made it so Lava rocks do not cast shadows and are disabled until Floor is Lava effect is applied

Made it so “difficulty” (which is not a normal option you can change on Portal) is set to 3 (Hard) so that zombies are a little more tough, without having to change their specific damage values across the board (especially since you can’t change sk values for fast zombies at all). With that being said, I also adjusted the zombie attack damage lol.

Due to this difficulty change, Floor is Lava damage had to be reduced, character flinch is much more substantial and turrets hurt a lot more than usual (chambers still passable though!)

Renamed hardcore maps to not include “randomized” in .bsp filename as trigger_transitions do not work with maps more than 32 characters.

Fixed water drown timer not resetting when getting in and out of the water repeatedly. A [user on Reddit did suggest to ClearIO instead of disabling drown logic](https://www.reddit.com/r/hammer/comments/1ijdrx3/comment/mbgacyh), and this seems to have worked

Random effect logic is more random now due to some entity setup.

Gave more of an “air channel” when Water Flood effect is applied to Chamber 00

Made it so a message appears on the screen of what effect is applied (thanks for suggestion by Renoloh on ModDB)

Renamed “Zombie Spawn” to Zombie Invasion. I’d like to change “Turret Spawn” too, but I dunno what to.

Changed auto-save order when entering a new chamber in the same map. Before, there was a chance you would accidentally get two effects on a normal playthrough.

Added test maps for both chambers so that way you can test all the different effects without trying to respin them over and over again.

### Instructions for testing
Turn on developer console in keyboard options

At the very beginning of map spawn or chamber elevator, pause and open up the console

Depending on what chamber you are in, you will have to type in a different command

I have made a list of all the different effects below, all you will have to do is copy past into the console and change the chamber number to the specific one you are on:
- ent_fire Chamber_00_Lava_Floor_Logic trigger
- ent_fire Chamber_00_Turret_Logic trigger
- ent_fire Chamber_00_Gravity_Logic trigger
- ent_fire Chamber_00_Speed_Logic trigger
- ent_fire Chamber_00_Zombie_Logic trigger
- ent_fire Chamber_00_Water_Logic trigger
- ent_fire Chamber_00_Dark_Logic trigger
- ent_fire Chamber_00_Gas_Logic trigger
- ent_fire Chamber_00_Size_Logic trigger
- ent_fire Chamber_00_Combine_Logic trigger

## Maps

- testchmb_a_00_randomized_v2
- testchmb_a_00_hardcore_v2
- testchmb_a_00_impossible_v2
- testchmb_a_00_test_v2
- testchmb_a_01_randomized_v1
- testchmb_a_01_hardcore_v1
- testchmb_a_01_impossible_v1
- testchmb_a_01_test_v1

## Additional Notes (in order)

Looked into adding support for a Combine Attack effect, but sadly combine do not have the ability to shoot bullets in Portal.
This is fixable, although I do not have the slightest clue how to fix it, even with instructions.
I would still love to implement this though so if you know how to help, it would be greatly appreciated!
[vigovproductions.net/interactive/npcs-shooting-portal](https://www.vigovproductions.net/interactive/npcs-shooting-portal.html)

Could also use combine_mine around the chambers with this or a separate effect but seems boring by itself.

[ModDB article asking about this](https://www.moddb.com/mods/portal-randomized/news/combine-mine-suggestions)

I did eventually think about spawning other combine entities, 
and the ones that seem to work is the rollermine, manhack and (surprisingly) the strider, which actually shoots!

### Zombie attack damages:
- sk_zombie_dmg_one_slash 25
- sk_zombie_dmg_both_slash 35
- sk_headcrab_melee_dmg 35

I wanted to add a Slippery Floors effect but turns out sv_friction isn’t available in Portal 1. Maybe one day?

---

Up to this point, I sent my friend Memes a copy of the pre-release demo for this version (up to Chamber 02). Find it on [Twitch](https://www.twitch.tv/videos/2389663639)!

{% include embed/twitch.html id='2389663639' %}

[ModDB Article regard this](https://www.moddb.com/mods/portal-randomized/news/memesrus-124-exclusive-demo-showcase)

### Observed during Memes stream:

#### I need a way to enable/disable effects without re-exporting the map
Fun Fact: You can use Ctrl+Shift+Alt+B to open a VGUI editor. I couldn’t figure this out though, 
since I wanted to try to edit the options menu or console to run commands from a button. 
As a workaround, suggesting using ent_fire commands to anyone who is wanting to test specific effects on the go. 
Gotta write documentation regarding this, and a map version of each map without any logic_auto firing at mapload needs to be created for testing purposes.

#### Drown timer not resetting sometimes
I thought I initially solved this issue before when I asked about getting this working on [Reddit](https://www.reddit.com/r/hammer/comments/1ijdrx3/comment/mbfbc8x)

I was able to replicate this by getting in and out of the water multiple times in a row. 
A [user on Reddit did suggest to ClearIO instead of disabling drown logic](https://www.reddit.com/r/hammer/comments/1ijdrx3/comment/mbgacyh), 
and this seems to have worked

#### [Random logic not randoming](https://www.twitch.tv/memesrus_124/clip/NiceDreamySowKappaClaus-eYRENxxfR0xFyJ-z)
Tricky one as source engine handles random logic through logic_case. Submitted a [Reddit post](https://www.reddit.com/r/hammer/comments/1ixjsce/logic_auto_with_logic_case_not_producing_a_truly/) to hopefully figure it out.

u/Poissonnoye suggested using different logic for the random effect picker, which does seem to yield more random results in my case. Rolling with it for now and will observe on future playtests of other users.

#### Playmodel Suggestion

Sable_PMA suggested effects that change the player model which would normally be done by cl_playermodel but that doesn’t seem to change it for whatever reason. 
Anyways by itself it doesn’t sound too interesting, but meme’s suggested maybe changing player size with it, 
which does sound interesting, and [can be done](https://www.reddit.com/r/hammer/comments/13ssffz/comment/jlt50y6).

The only problem with this is that setting the player model scale to be .5 (or half) 
works just fine, setting to anything above the normal 1 will cause glitchy collisions when jumping, 
getting you stuck in this animation and in an object until you noclip out.

There is probably a way of fixing this, but it would require some source engine coding and such.

Since I do like the small model effect and it doesn’t seem to break anything, I am curious to see if you all prefer to have this in first or third person. I set a poll on ModDB: https://www.moddb.com/mods/portal-randomized/polls/first-or-third-person-small-chell

---

## Edits

There are none yet, but if I do happen to edit anything noteworthy, I will notate here!

---

All of my posts have a comment section beneath them, powered by [Giscus](https://giscus.app/).

Did I get something wrong? Do you hate my opinion? Do you have additional thoughts about my blabbering???

**Leave a comment!**

Note this does require a GitHub account.