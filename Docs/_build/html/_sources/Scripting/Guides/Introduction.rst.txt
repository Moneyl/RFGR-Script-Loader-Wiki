Introduction
********************************************************

Here you'll find all the info you need to start writing lua scripts for RFGR. While traditional modding involves editing existing data files to change the properties and behavior of the game, lua scripting allows for a much more dynamic modding experience. Some of the advantages of lua scripting are:

- You aren't restricted to editing existing data found in xtbls, due to the nature of the RSL the game can be opened up much more than before. 
- Lua scripts are responsive and can change their behavior over time, unlike xtbls which are simply static data files.
- You can edit lua scripts live instead of needing to restart -> unpack -> edit -> repack -> test -> repeat for even the smallest of changes. The higher iteration rate should speed up mod development and reduce hair pulling.

.. warning:: RSL is still in early stages of development. As such, you may find incomplete features, bugs, and experience breaking changes in updates. Keep this in mind before using it in it's current state.

Calling lua scripts
========================================================
Currently calling lua scripts is as simple as placing a .lua file in your Scripts folder, ```Red Faction Guerrilla Re-MARS-tered\RFGR Script Loader\Scripts``` and running it through the built in script editor, or script select menu. You might need to hit the refresh button if the script was created externally after RSL was started. 

You can also open the built-in script editor after loading RSL and save/load/create scripts right from the game. It's good for quick edits and testing, but I'd still recommend using an external editor for major editing.

A later release will feature more advanced methods for loading and running scripts. Likely having each script, set of scripts, or mod, be it's own package with information like version, and dependent packages.

Core library
=========================================================
The core library, in ```Red Faction Guerrilla Re-MARS-tered\RFGR Script Loader\Core```, includes useful functions, and types. It's loaded when RSL is started. You generally shouldn't distribute edits to this with a mod as it's meant to be a common library that all users have. You should however take a look at it. There are many useful values defined in the core library which are referenced in the docs.

One example of this is ObjectTypes.lua, which defines the table ```rfg.ObjectTypes```. This table has all object types (which will be discussed more in the next section), and their corresponding integer values, which can be used to sort objects by type. 

Objects
=========================================================
RFGR considers many things in the game world to be objects. Many of the things you can see in the game are objects, such as the player, humans, or vehicles, and even some things you can't see, like spawn points and cliff killzones. You can see a full list of object types in ObjectTypes.lua, or in the ObjectTypes page here in the docs.

Since objects are so pervasive, being able to access them is key to interacting with the game world. 

Accessing objects
---------------------------------------------------------
There are several ways to access objects... 