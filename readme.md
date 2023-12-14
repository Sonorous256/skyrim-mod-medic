![logo](https://github.com/Sonorous256/skyrim-mod-medic/blob/master/logo.webp)

# "Mod Medic" (working title) Skyrim mod auditioning, inspecting and troubleshooting

* View files and records within skyrim mods
* Inspect how mod files overwrite each other and interact
* Audition or compare mods by seeing the effect of enabling/disabling a mod instantly in 3d preview
* Perfect your modlist by getting every little detail right before you even start the game
* Understands how Mod Organizer 2 arranges and stores mods
* Fast loading and modern style UI

This is an early pre-release alpha version -- jankiness is expected. You will probably encounter bugs.

The Skyrim ecosystem has gotten so broad (and the underlying Skyrim architectures are so odd/janky themselves) that it may take some time before everything can work perfectly for everyone.

In particular, I'm looking for feedback on:

* Do you get a problem that appears like a hardware compatibility issue? (There's some pretty complicated 3d tech behind the scenes)
* Do you get frequent crashes or error messages?
* Are there specific mods on your modlist that appear to cause problems?

Also:

* Do you have specific ideas/requests for features that could be useful for a particular use-case for you?

## First steps

Try selecting an actor from the "Actors" panel, open the "Actor Brkdwn" to see details<br/>
Now try enabling and disabling mods from the "Mods" panel<br/>
The 3d preview will show the effect of disabling a mod immediately<br/>

Open and close panels using the buttons in the bottom bar<br/>
Left panels are for finding and selecting objects: like actors, cells, records and files<br/>
Middle panels show detailed information<br/>
Right panels for to enable/disable mods and change rendering settings<br/>

Camera controls<br/>
Right-click and drag to look around<br/>
W,A,S,D to move about (in Cell mode)<br/>
Hold shift or ctrl to effect speed<br/>
Ctrl+R to reset to a default position<br/>

## Next steps

This is the kind of project that needs to grow over time. I don't see this as a finished or complete project.
The exact future may depend on what is most needed by users.
But it might include things like lighting modes, support for different types of data -- sounds, navmesh, weather -- or anything else that might be possible with this tech.

Though this project contains some elements of things like record viewers, nif tools, bsa browsers, etc, it's not really intended as a replacement for existing tools. The main focus is features that are unique to this project, such as understanding the makeup of mods and previewing compound objects.

## Notes

Only tested in english, with Skyrim AE and on a recent version of Windows. It should work more broadly, but I'm not sure about language support.

** Don't run from within Mod Organizer 2 **! Just run like a normal program.
Also, probably don't install into your Skyrim directory.

Visual effects that are very specific to Skyrim -- water, fire, light rays, etc -- generally aren't supported. They require very special case emulation and so have less favorable effort/usefulness tradeoff.

See my other tool, "Xenoviewer" for Starfield on Nexus.

## Troubleshooting

Mod Medic will cache some files in your %USERPROFILE%/AppData/Local/Temp/skyrim-mod-medic directory. If you run into problems, you can try deleting this folder.

## Acknowledgements

Many thanks and regards to the people that have contributed to understanding to skyrim formats, such as the contributors of the en.uesp.net wiki.
Also thanks to the author of NifSkope (which I expect many readers already use, but if not -- check it out). Though mod-medic has it's own cross-game parsing tech, one of the configuration files is partially based on a configuration file from NifSkope.

