![logo](https://github.com/Sonorous256/skyrim-mod-medic/blob/master/logo.webp)

# "Mod Medic" Skyrim mod troubleshooting, investigation and auditioning

* View files and records within skyrim mods, with 3D preview and detailed hex view
* Investigate how mod files overwrite each other and interact -- find conflicts and unwanted overwrites
* Audition or compare mods by seeing the effect of enabling/disabling a mod instantly in 3D preview
* Perfect your modlist by getting every little detail right before you even start the game
* Fast loading and convenient modern style UI
* The tool understands how Mod Organizer 2 arranges files and record tables into "mods"

This is an early build -- jankiness is expected. You will probably encounter bugs.

The Skyrim ecosystem has gotten so broad (and the underlying Skyrim architectures are so odd/janky themselves) that it may take some time before everything can work perfectly for everyone.

If you run into problems with specific mods (or just hit some kind of blocker), stop by:
* Discord: [https://discord.gg/hJyzCBJwTE](https://discord.gg/hJyzCBJwTE)
* Nexus: https://www.nexusmods.com/skyrimspecialedition/mods/108357

## Installation

No formal install/uninstall required
* Copy files anywhere
* Run mod-medic.exe (do *not* run from within Mod Organizer)

## First steps

Try selecting an actor from the "Actors" panel, open the "Actor Brkdwn" to see details<br/>
Now try enabling and disabling mods from the "Mods" panel<br/>
The 3d preview will show the effect of disabling a mod immediately<br/>

Open and close panels using the buttons in the bottom bar<br/>
Left panels are for finding and selecting objects: actors, cells, records and files<br/>
Middle panels show detailed information<br/>
Right panels enable/disable mods and change rendering settings<br/>

Camera controls<br/>
Right-click and drag to look around<br/>
W,A,S,D to move about (in Cell mode)<br/>
Hold shift or ctrl to effect speed<br/>
Ctrl+R to reset to a default position<br/>

## Next steps

This is the kind of project that needs to grow over time.
The exact future may depend on what is most needed by users.
But it might include things like lighting modes, support for different types of data -- sounds, animation, navmesh, weather, lods -- or anything else that might be possible with this tech.

Feature requests may be voted on the near future. Join our discord ([https://discord.gg/hJyzCBJwTE](https://discord.gg/hJyzCBJwTE)) if you want to contribute.

Though this project contains some elements of things like record viewers, nif tools, bsa browsers, etc, it's not really intended as a replacement for existing tools. The main focus is features that are unique to this project, such as understanding the makeup of mods and previewing compound objects.

## Command line options

This is a GUI tool, but there are command line options to assist with hardware compatibility and integration with scripts and other tools.

| Flag | Description |
| ---- | ----------- |
| --hcm | Force hardware compatibility mode (usually only required for integrated GPUs) |
| --skipcfg | Use the same configuration options as last time, and skip the configuration dialog |
| --skipgputweakcheck | Don't look for Asus "GPU Tweak" software |
| --version / -v | Write app version to standard out and exit |
| --help / -h | This message | 
|||
| --skyrimCode (uint32) |  Find record by the id, as it would appear in the game. The top 8 bits are related to table id. Prefix hex with 0x |
| --recordId (uint32) | Find record by id. Can be combined with "tableName" |
| --tableName (string) | Record table to search in. Use filename with extension, but no path. Eg, "dawnguard.esm" |
| --editorId (string) | Find record by "editor id" (as seen in Creation Kit) |

So, for example, if you want to jump to a specific cell/actor, you can use something like "--editorId Eola --skipcfg" or "--tableName skyrim.esm --recordId 0x0001990f --skipcfg"

## Links

Nexus Mods: https://www.nexusmods.com/skyrimspecialedition/mods/108357
Discord: [https://discord.gg/hJyzCBJwTE](https://discord.gg/hJyzCBJwTE)
Github mirror: https://github.com/Sonorous256/skyrim-mod-medic

This software will be distributed via the Nexus and Github links above. If you did not receive this file from one of those two locations, your distribution may be compromised and dangerous.

## Gotchas

- "Batched patch", "smashed patch", etc, can make things confusing when turning mods on and off. Consider turning them off if you get weird things happening
- The order of things in the "mod list" is not the same as the table load order. It's the same as the mod list order in MO2
- If you have the mod "Expressive Facegen Morphs SE" (or something similar) it will take effect when the "Regenerate Customization" flag is enabled -- so you may want to try toggling this mod on and off
- Some armor character parts may not appear. This is usually because the nif file or TXST record refers to a texture that doesn't exist
- Some characters may not be wearing their gear. This is because in some cases the "Worn Armor" attribute has the characters actual gear and "Default Outfit" has either nothing or body parts -- and in other cases it is flipped. I haven't quite figured out how Skyrim handles these attributes exactly yet.
- When using Vortex you and turn .esp/.esl/.esm files on and off -- but when using Mod Organizer 2, you instead turn entire mods on and off. In short, things just work better with Mod Organizer 2
- Some things (like textures, nif files, etc) may hot-reload if they change on disk.
- On a high-res screen the text will ve very small. This is because the Windows GUI "Scale" setting is not supported (sorry, it's honestly a real hassle!)
- Many characters will have a neck gap. This is because the character "weight" value isn't supported for the body yet, but the pregenerated heads already have it built in.
- the camera is often at an awkward spot when you load a new cell -- often pressing ctrl+R will look, but sometimes you have to search around

## Troubleshooting

Mod Medic will cache some files in your %USERPROFILE%/AppData/Local/Temp/skyrim-mod-medic directory. If you run into problems, you can try deleting this folder.

## Acknowledgements

Many thanks and regards to the people that have contributed to understanding to skyrim formats, such as the contributors of the uesp.net wiki.
Also thanks to the author of NifSkope (which I expect many readers already use, but if not -- check it out). Though mod-medic has it's own cross-game parsing tech, one of the configuration files is partially based on a similar configuration file from NifSkope.
(further acknowledgements will appear here shortly)
