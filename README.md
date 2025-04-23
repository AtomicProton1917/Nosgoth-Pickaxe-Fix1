# CONSOLE COMMANDS 
Press the Tilde ~` button (it's the first one under Escape) to open the console.

You can unstuck yourself by typing "Reconnect" 

You can find the best sensitivity for your mouse by not touching the in-game setting and instead typing "SetSensitivity 11" (without the "", start with 11 and increase/decrease) 

F1 opens a log that shows who has multi-kills, helps you know when to turn off hacks by showing when a spectator joins, and probably other features I haven't noticed.

# - About the ⛏ Performance Fix. 
It only includes known information that I couldn't find in the FAQ, and it's intended to resolve issues with Nosgoth when it plays poorly or appears to be off, even with the lowest in-game settings. Character movements *feel* weird, maybe you are landing less last moment shots lately, that could save your life because you are "too slow, it lagged, and your alchemist's bombs didn't shoot even tho you heard it" & other weirdness that shouldn't happen as often or at all. It has an insidious way of breaking, especially if you followed FAQ 11 on Discord and used dxvk's advantages to play higher graphics settings. It will be playable (less prone to crashing) on higher presets, but it won't remain stable for more than a few matches at best without requiring a restart. It will make the game difficult beyond the obvious statement of more unnecessary details and lights blocking your view.
 I could only use graphics for a few days until I performed a fresh install, as the game became annoying. Watching an old Nosgoth video made it clear that not even the lowest in-game graphics preset plays correctly without some tweaks on certain hardware combinations.


# 𝟙. Reinstall & optimize driver + in-game settings for stable fps and low input lag

⚫ Do a clean reinstall, incl. the mod, and make sure the entire documents\my games\nosgoth folder is removed (Revo Uninstaller does the trick)

⚫ Dxvk may increase stability or not, depending on your system. To try using it, place the files here. 

[drive-letter]\SteamLibrary\steamapps\common\nosgoth\Binaries\Win32 

https://github.com/doitsujin/dxvk/releases/download/v2.5.3/dxvk-2.5.3.tar.gz

https://github.com/doitsujin/dxvk/releases/
  
If the game has issues running with DXVK, delete its files to uninstall


To play it safe, apply all changes in this guide before launching the fresh installation.


⚫ Set up the Video Driver Optimizations below 

Note: These driver settings can also have a positive impact on  other PvP or fast-paced games.

 # NVIDIA

Open Nvidia Control Panel and select Manage 3D settings > Program Settings > Add Game > *select nosgoth from the list or add nosgoth.exe manually*

Anisotropic filtering > off

Antialiasing > off

Low Latency mode > Ultra (this is a must)

Power management mode > Prefer maximum performance

Texture filtering - Anisotropic sample optimization > OFF

Texture filtering - Negative LOD bias > Allow

Texture filtering - Trilinear optimization > ON

Vertical sync > OFF (this is a must)

Virtual Reality pre-rendered frames > 1


# AMD

Similar to NVIDIA, but if they are named differently or missing, Google can assist. 
Whatever lowers input lag and increases the performance of the game

# After launching the game
Go  to video settings

Limit fps to 80-100 
(This is important; you want stable FPS that doesn't drop, regardless of how many frames it peaks at.) Because FPS affects the speed of the game, it will gradually decrease the more time Nosgoth runs, becoming unstable and resulting in increased amounts of FPS drops when the game gets heated. High fps will give you very low input lag, but characters will become slower. The sweet spot between input lag and slow characters is 80 to 100)

 FPS under 60 is considered cheating.

80 fps for servers close to you (EU players on EU server) or 100+ fps on far servers (EU players on US server)

Make sure VSYNC is disabled.

Enable Borderless Window and Background Audio (fullscreen is more stable, but it causes crashing when you alt+tab to wait in queue.)


# 𝟚. Extra steps to stabilize your framerate (this can be skipped if DXVK does its job properly, assuming you have a lot of RAM.)
Notes: These two "pre-made" config files will modify your in-game settings, balancing them to accommodate the game's capabilities and minimize memory leaks, especially on modern hardware.
Repeating step 1 would be a good idea if you booted the game before proceeding to this part and want to avoid risks. What will break Nosgoth is unpredictable; at some point, switching audio from speakers to headphones caused it to crash, until I upgraded the PC's motherboard.

 ⚫ .ini File Locations

DefaultSystemSettings.ini is located in your SteamLibrary\steamapps\common\nosgoth\BCMPGame\Config folder.

BaseSystemSettings is located in your SteamLibrary\steamapps\common\nosgoth\Engine\Config folder.

 ⚫ Replace the text in DefaultSystemSettings.ini with this 

https://github.com/AtomicProton1917/Nosgoth-Pickaxe-Fix1/issues/1

 ⚫ And BaseSystemSettings.ini with this 

https://github.com/AtomicProton1917/Nosgoth-Pickaxe-Fix1/issues/2



# 𝟛. Create your config manually
Back up the .ini files before modifying them, as changing those values can easily render the game unplayable.


DefaultSystemSettings.ini is where you can customize each in-game graphic setting.

In BaseSystemSettings.ini, you should use the highest values you set for any preset in DefaultSystemSettings.ini

To decrease a specific texturegroup resolution, use one of the numbers below to replace its MaxLOD

This is an example of how it should look.

TEXTUREGROUP_Skybox=(MinLODSize=1,𝐌𝐚𝐱𝐋𝐎𝐃𝐒𝐢𝐳𝐞=𝟐,LODBias=0,MinMagFilter=Aniso,MipFilter=Point,MipGenSettings=TMGS_SimpleAverage)

# TEXTUREGROUPs MaxLOD numbers

2, (using this on character/world/weapon groups will make them look straight out of a 3d printer) 

8,
 
16,
 
32, 
64, 
128,  
256, 
512, 
1024, 
2048, 

Swapping True and False will enable or Disable, and generally, 0 will apply the lowest available option for stuff that uses numbers.

 # For example.
 
DetailMode=0

MaxDrawDistanceScale=1.000000

ShadowFilterQualityBias=0

MaxAnisotropy=0

MaxMultiSamples=0

Increasing MaxDrawDistanceScale=1.000000 to 3.000000 will make things like grass not pop up in your view but your game will crash faster than a flying chicken. Setting it to 0.000000 will only display health stations and players, with everything else in the game rendered black. 



If the game weren't so broken, these files could be used to push Nosgoth's graphics to their limits, rather than resorting to the sledgehammer treatment, so that they play as they should.
This is also how you can play the game on a toaster.
If I made any mistakes while writing this, please let me know, and I will correct them as soon as possible.
