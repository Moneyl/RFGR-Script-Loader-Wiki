Introduction
********************************************************

Here you'll find all the info you need to start writing lua scripts for RFGR. While traditional modding involves editing existing data files to change the properties and behavior of the game, lua scripting allows for a much more dynamic modding experience. Some of the advantages of lua scripting are:

- You aren't restricted to editing existing data found in xtbls, due to the nature of the RSL the game can be opened up much more than before. 
- Lua scripts are responsive and can change their behavior over time, unlike xtbls which are simply static data files.
- You can edit lua scripts live instead of needing to restart -> unpack -> edit -> repack -> test -> repeat for even the smallest of changes. The higher iteration rate should speed up mod development and reduce hair pulling.

.. warning:: RSL is still in early stages of development. As such, you may find incomplete features, bugs, and experience breaking changes in updates. Keep this in mind before using it in it's current state.

Calling lua scripts
========================================================
Currently calling lua scripts is as simple as placing a .lua file in your Scripts folder, ``Red Faction Guerrilla Re-MARS-tered\RFGR Script Loader\Scripts`` and running it through the built in script editor, or script select menu. You might need to hit the refresh button if the script was created externally after RSL was started. 

You can also open the built-in script editor after loading RSL and save/load/create scripts right from the game. It's good for quick edits and testing, but I'd still recommend using an external editor for major editing.

A later release will feature more advanced methods for loading and running scripts. Likely having each script, set of scripts, or mod, be it's own package with information like version, and dependent packages.

Core library
=========================================================
The core library, in ``Red Faction Guerrilla Re-MARS-tered\RFGR Script Loader\Core``, includes useful functions, and types. It's loaded when RSL is started. You generally shouldn't distribute edits to this with a mod as it's meant to be a common library that all users have. You should however take a look at it. There are many useful values defined in the core library which are referenced in the docs.

One example of this is ObjectTypes.lua, which defines the table ``rfg.ObjectTypes``. This table has all object types (which will be discussed more in the next section), and their corresponding integer values, which can be used to sort objects by type. 

Objects
=========================================================
RFGR considers many things in the game world to be objects. Many of the things you can see in the game are objects, such as the player, humans, or vehicles, and even some things you can't see, like spawn points and cliff killzones. You can see a full list of object types in ObjectTypes.lua, or in the ObjectTypes page here in the docs.

Since objects are so pervasive, being able to access them is key to interacting with the game world. 

Accessing objects
---------------------------------------------------------
There are several ways to access objects. The first way to is use ``rfg.GetObject``. It takes a string, which is the name of the object you're looking for. This isn't the most reliable way of finding objects, as a large percentage of them are nameless. Still, it can be useful for easily finding known objects like Samanya, or specific map districts. It can be used like so:

.. code-block:: lua

    Sam = rfg.GetObject("Samanya") -- Get samanya's object
    rsl.Log(Sam.Position.GetDataString()) -- Log Sams x,y,z position

    --[[ Currently Sam is an Object type. To access variables 
    specific to Humans such as Human.StealthPercent you'll need
    to cast her variable to a human type. This can be done like so...--]] 

    SamAsHuman = Sam:CastToHuman()
    rsl.Log(toString(SamAsHuman.StealthPercent)) -- Prove that it worked by accessing a human specific variable

    -- Alternatively, you can reuse the existing variable
    Sam = Sam:CastToHuman()
    rsl.Log(toString(Sam.StealthPercent))

Note that if you tried accessing a human specific variable (or other derived types variable) before casting to that object type you should experience an error when running the script. As shown in this next example:

.. code-block:: lua

    Sam = rfg.GetObject("Samanya") -- Get samanya's objects
    rsl.Log(toString(Sam.StealthPercent)) 
    -- Bad! This will cause an error as you're trying to access a Human variable before casting Sam to a Human type

This applies to accessing objects no matter which method you use to access them.

You can also find objects with their handle via ``rfg.GetObjectByHandle``, which works in the same way, but instead takes an unsigned integer argument. You can find object handles in many types. For example, ``Human.ShieldHandle`` is the object handle of that humans shield if they possess one.

.. important:: As of release 0.4.0 not all object types have been bound to lua yet due to time constraints. Therefore you can only cast to a few of them for now. The available object types for 0.4.0 are Human, Player, Zone, and District. For all other object types you'll only be able to access variables available to all `objects`_.


The next way to access objects is by iterating through the world object list. This is a list of all objects in the game world. The object list can be found in the rfg world table. This method is useful for when you're looking for an unnamed object, or if you wish to change all objects of a certain type, like vehicles for example. You can access the world table directly through ``rfg.ActiveWorld`` or create your own variable to reference it with ``your_var = rfg.GetWorld()``. 

From here you can use a loop to run through the object list, object by object, and perform your changes. Here's an example that loops through the object list, and counts the number of humans in the list.

.. code-block:: lua

    HumanCount = 0
    for i=0, rfg.ActiveWorld.AllObjects:size(), 1 do
        CurrentObject = rfg.ActiveWorld.AllObjects[i] -- Make a reference variable to the current object for convenience.
        if CurrentObject.Type == rfg.ObjectTypes.Human then -- Check if current objects type matches the value for Humans
            HumanCount = HumanCount + 1
        end
    end

    rsl.Log("HumanCount: " .. toString(HumanCount))

Note that while lua tables use 1 based indexing, the rfg object list uses 0 based indexing. This is a side effect of c++ using 0 based indexing, but, this may be changed in a future update to avoid inconsistency with existing lua standards.

Where to go from here
=====================================================================
There are many other functions, types, and values available to scripts. Too many to list here. To see a list of functions and tables available to scripts and details about their usage you should look at the `namespaces`_ page. The `types`_ page has a list of types available to scripts. For more usage examples you should read the rest of the guides, and look through some of the `examples`_ provided. If you'd like to contribute the the docs you should read `contributing`_.

.. _`namespaces`: ../Namespaces.html
.. _`types`: ../Types.html
.. _`contributing`: ../../Contributing.html
.. _`examples`: ../Examples.html
.. _`objects`: ../Types/Object.html