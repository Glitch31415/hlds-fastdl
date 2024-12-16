-------------------------
blockmaker_v4.01 by Necro
-------------------------
This plugin was inspired by FatalisDKs bunnyhop course maker (BCM).
Thanks to SpaceDude for the basics of the grab code from his JediGrab plugin.

I made this for use on hide n seek servers but of course you can use it however you please!

Thanks to 'crazyFingers Pat' and 'SloCal Jack Daniels' for help with the custom model textures.
Thanks to 'Gangien' for assistance with the small and large blocks.
Thanks to 'minimiller' for writing the installation help and FAQ documents.

Features:
- Say /bm in chat to bring up the main menu.
- Bind a key to +bmgrab to move the blocks around.
- While grabbing a block, press attack1 to copy a block, attack2 to delete, jump to move a block closer, and duck to move a block further away.
- Create a block by aiming at the floor or a wall.
- Convert block you are aiming at to the selected block type.
- Delete block you are aiming at.
- Rotate the block you are aiming at.
- Optional noclip and godmode to make creating blocks easier.
- Snapping option so when creating and moving blocks, they snap into place next to, above or below other nearby blocks. 
- Snapping gap option to leave a gap between blocks when they snap together.
- Save all blocks to file using mapname, will load on map load. Save folder: \amxmodx\blockmaker\
- In game plugin help including server CVAR values.
- Look at a block to see what type of block it is.
- Server Ops can edit the 'blockmaker_models.ini' file to specify alternative block models and rendering

CVARs:
- bm_telefrags 1 (Players near teleport exit die if someone comes through)
- bm_firedamageamount 20.0 (How much the fire damage block hurts per half second)
- bm_damageamount 5.0 (How much the damage block hurts per half second)
- bm_healamount 1.0 (How much life the healer block gives per half second)
- bm_invincibletime 20.0 (How long invincibility lasts in seconds) 
- bm_invinciblecooldown 60.0 (Seconds before invincibility can be used again)
- bm_stealthtime 20.0 (How long stealth lasts in seconds)
- bm_stealthcooldown 60.0 (Seconds before stealth can be used again)
- bm_camouflagetime 20.0 (How long camouflage lasts in seconds)
- bm_camouflagecooldown 60.0 (Seconds before camouflage can be used again)
- bm_nukecooldown 60.0 (Seconds before the nuke can be used again)
- bm_randomcooldown 30.0 (Seconds before the random block can be used again)
- bm_bootsofspeedtime 20.0 (How long the boots of speed last for in seconds)
- bm_bootsofspeedcooldown 60.0 (Seconds until boots can be used again)
- bm_autobhoptime 20.0 (How long the player has auto bhop)
- bm_autobhopcooldown 60.0 (Time before auto bhop can be used again)
- bm_teleportsound 1 (Teleporters make a sound when something passes through them)

Block types:
- Platform (A platform you can stand on)
- Bunnyhop (A platform that disappears for a short period of time after touching it)
- Damage (Hurts you if you stand on top of it)
- Healer (Heals you if you stand on top of it)
- No Fall Damage (You don't take any damage if you fall onto it)
- Ice (You slide around like you're on ice)
- Trampoline (Throws you up in the air)
- Speed Boost (Throws you forwards in the direction you're looking)
- Invincibility (Player becomes invincible for a set amount of time)
- Stealth (Player becomes invisible for a set amount of time)
- Death (Player dies instantly)
- Nuke (Destroys all players on the other team unless a player has invincibility)
- Camouflage (Player looks like the other team for a set amount of time)
- Low Gravity (Jumping from this block you get low gravity until you land) (Thanks C$L for idea)
- Fire (Another damage block but nicer looking) =)
- Slap (You get slapped!) (Pat made this one)
- Random (Random between Invincibility, Stealth, Camouflage, Boots Of Speed, a slap, or death!)
- Honey (Player moves slowly like they're stuck in honey) (Thanks C$L for idea)
- CT Barrier (Only Terrorists can pass through these blocks, acts as solid for Counter-Terrorists)
- T Barrier (Only Counter-Terrorists can pass through these blocks, acts as solid for Terrorists)
- Boots Of Speed (Player runs fast for a set amount of time)
- Glass (Same as platform but looks like a transparent pane of glass)
- Bunnyhop - No slow down (Same as bunnyhop block but you don't slow down after landing)
- Auto bunnyhop (Player can hold jump to auto bunnyhop for 'bm_autobhoptime' amount of time)

Changing Block Models:
- New in version 3.60 is the ability to change the block models and the rendering of the blocks without editing the code.
- To do this, edit the file called 'blockmaker_models.ini' in the '/amxmodx/configs/' folder.
- Each line in the file can have a maximum of 7 parameters separated by white space.
- The 1st is the ID of the block, 2nd is the path and filename of the model, 3rd is the rendering type, 4th, 5th, 6th & 7th are the
- red, green, blue and alpha values for various glowing styles.
- The path to the model is relative to the '/cstrike/' folder. Folders in the path can be separated with either / or \.
- If you want to use the default block model but want to change the rendering of it then use 'DEFAULT' as the path.
- If at any time no information is specified or is invalid then default values are used.
- The different rendering types are:
- 
- 	GLOWSHELL	-	Solid model with a glowing shell (The invincibility block uses this with white colour values and alpha 16)
- 	TRANSCOLOR	-	Transparent model with a glowing shell (No default block uses this rendering type)
- 	TRANSALPHA	-	Transparent model (By default the glass block looks like this with an alpha of 50)
- 	TRANSWHITE	-	Bright white transparent model (By default the stealth block looks like this with an alpha of 100)
- 
- The TRANSALPHA and TRANSWHITE rendering types do not make use of the red, green and blue values.
- Here is a short example of a 'blockmaker_models.ini' file:

PLATFORM	models/blockmaker/myblock_platform.mdl GLOWSHELL 0 255 0 16
BHOP		models/blockmaker/myblock_bhop2.mdl TRANSALPHA 255 255 255 150
DAMAGE		models/steves_dmg_block.mdl
HEALER		DEFAULT GLOWSHELL 0 0 255 16

- The platform block would use a different model in the '/models/blockmaker/' folder and would glow green with a magnitude of 16.
- The bhop block would use a different model in the '/models/blockmaker/' folder and would be semi-transparent with an alpha of 150.
- The damage block would use a different model in the '/models/' folder and wouldn't glow at all.
- The healer block would use the default model and would glow blue with a magnitude of 16.
- All other blocks would use their hard-coded default values.
- The speed boost, trampoline and fire blocks will always have their sprites on top.
- The only blocks with default rendering are the invincibility, stealth and glass blocks.
- The plugin will automatically look for models with filename suffixed with _large and _small for the larger and smaller blocks.


-------------------------
Version 4.01 Changelist
-------------------------
- Fixed bug that allowed non-admins to create long jumps! (Oops!)


-------------------------
Version 4.00 Changelist
-------------------------
- Restructured main menu.
- Added small and large blocks!
- Added Timer to create a course, complete with scoreboard. Say /bm15 to view times.
- Added Measuring Tool to measure distances between 2 blocks or timers and 2 points.
- Added Long Jump Creator to easily create long jumps of selected size.
- Added ability to swap start and destination of teleports.
- Added 'bm_teleportsound' CVAR to enable/disable teleport sound.
- Plugin now requires 'fakemeta' for using the Timer start and stop buttons.
- Fixed bug where teleport menu would close after using noclip.
- Fixed bug that creates an unused folder in '/amxmodx/configs/'.


-------------------------
Version 3.60 Changelist
-------------------------
- Added block types: Glass, Bunnyhop (No slow down), Auto Bunnyhop.
- Fixed bug where all players could group blocks.
- Removed old loading style.
- Added 'blinkarrival.wav' warcraft3 sound to zip file (was missing before).
- Added 'blockmaker_models.ini' to specify alternative block models and rendering.
- Added Auto Bunnyhop block to random block.
- Added new block model for the stealth block! :)


-------------------------
Version 3.51 Changelist
-------------------------
- Fixed bug that allows all players to rotate blocks.


-------------------------
Version 3.5 Changelist
-------------------------
- Added block types: Invincibility, Stealth, Death, Nuke, Camouflage, Low Gravity, Fire, Slap, Random, Honey, CT & T Barriers, Boots Of Speed.
- Added CVARs for invincibility, stealth, nuke, camouflage, and boots of speed times. 
- Added dynamic block selection menu so blocks can be added with ease. (No messing with menus)
- Added the ability to rotate blocks. (Blocks can now be vertical and horizontal).
- Added the ability to group blocks together and carry out an operation on multiple blocks.
- Main and teleport menus now contain noclip and godmode toggling.
- Blocks are now deleted when they're stuck. (Instead of when you're just not aiming at a block after releasing it).
- Improved snapping. (Re-wrote the function to allow for vertical blocks).
- Added snapping gap option.
- Added delete all blocks option.
- Added delete all teleports option.
- Added load from file option.
- Added a yes/no menu for some options to prevent accidental use.
- Changed the saving/loading method. (You won't see any difference).
- Using different no fall damage method to prevent godmode bug when using some HNS plugins.


-------------------------
Version 1.5 Changelist
-------------------------
- Removed glowing on all blocks and replaced with a separately textured model for each one.
- Added trampoline and speed boost blocks.
- Added a teleporter.
- Removed ground snapping. This fixed the bug where blocks would appear in mid-air on some maps.
- Prevented blocks from being placed underground or in walls where they can get lost.
- Introduced an options menu for godmode and noclip instead of scrolling through in main menu.
- Added 'bm_telefrags' CVAR to control whether or not players near teleport exit die if someone comes through.


-------------------------
Version 1.1 Changelist
-------------------------
- Made moving blocks while grabbed much smoother!
