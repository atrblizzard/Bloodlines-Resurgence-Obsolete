Bloodlines Resurgence (Swarm engine)
=====================================

============================================================
Description
============================================================
Bloodlines Resurgence is a community effort to update the original
Vampire Bloodlines game, bringing it to the current Source engine.
To achieve this, a dedicated team of hobbyists are working on
converting the original content into the new engine. This has the
following benefits: 

- Fixing all of the bugs still found in the original games
  (the original developers were only able to release one
  patch - it's up to us!) 
- Among these bugs were slowdowns, bad framerates, quest issues,
  graphical problems/glitches, and a serious control issue present
  for most people that locks up all controls for several moments
  periodically. 
- To bring the fans of the game an SDK to work with 
- This allows fans to make their own Bloodlines content - maps,
  textures, quests, npcs - anything and everything 
- Using the latest engine, Alien Swarm, to provide a smaller base
  with improvements over the old engine

Thanks to Sandern for the scratch Alien Swarm code base.

More information can be found at bloodlinesresurgencemod.com

==============================================================
Usage
==============================================================
1. Copy the resurgence folder into your sourcemods directory.
2. Open resurgence_sdk.sln in Visual Studio 2010.
3. A script is included to automatically copy the binaries
   into the mod bin folder (dllcopy.wsf). Modify this script
   if you want to change the output path (or remove it and 
   change the output paths in Visual Studio).
4. Compile
5. Check if binaries are copied correctly into your mods bin folder.
6. Either run pakfiles.bat (in the mod folder) or specify "-override_vpk"
   in the launch parameters. Otherwise some files will be overriden
   by the Alien Swarm files (for example, scripts/HudLayout.res).
6. Start the mod, open the console and type "map sdk_teams_hdr".

Note, the repository is not coming with compiled binaries, else
it will start the mod with the Swarm binaries!

==============================================================
VPK
==============================================================
The Alien Swarm VPK files take priority over the mod files.
To solve this use either the "-override_vpk" or pack the files
being overriden in a vpk file (see pakfiles.bat/txt).

==============================================================
Sounds
==============================================================
When the file "maps\soundcache\_master.cache" is not present,
it will rebuild the audio cache the next time you start the mod.
When you make changes to sounds, you will need to execute 
snd_updateaudiocache.

==============================================================
Base Code Changes
==============================================================

- Changed hardcoded scheme colors in basemodpanel.cpp, basemodframe.cpp, 
  vhyribbutton.cpp, nb_header_foot.cpp, nb_button.cpp.
- Added support of reading custom resource file in main menu when
  widescreen is set.
- Changed loading poster and progress bar in vloadingprogress.cpp
- Removed few unneeded Xbox 360 codes from GameUI
- Changed background video from nb_header_footer.cpp

==============================================================
Assets
==============================================================

Models:
- Included pistol and Mac10 submachine gun model
- Included items and hands models
- Made the weapons to include the hands models and attach to its bones

Resources:
- Included original background video and background music
- Changed main menu to suit the original 
- Changed loading screen and included variable poster background image
  support to suit the original (check interface/tipinfoscreen/background_x
  where x is a number)

Materials:
- Included needed materials for GUI, HUD, weapon and item models

Scripts:
- Changed weapon scripts to use Bloodlines models and sounds
- Changed loading background image to Bloodlines
- Changed keyboard control to use the default Half-Life 2 one

Sounds:
- Included weapons sounds

==============================================================
Unfinished Codes
==============================================================
Things to expect to be still unfinished/work in progress.

- Currently the muzzleflash is broken and has to be redone
- Third person weapon model won't attach to player model since
  it expects different bones, so until the Bloodlines player 
  models are not included, they will not attach properly 
- Default HL2 HUD (for now)
- VTMB font needs to be installed manually (can be found in
  resource folder