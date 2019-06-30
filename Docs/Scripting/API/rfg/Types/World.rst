
.. attention:: This page is incomplete and needs better descriptions and research into the behavior of the variables.


World
********************************************************
The rfg world structure. Contains the global list of all objects in the game and info about each of the world zones.

Variables
========================================================

**MissionObjectCreationMode** (`bool`_)
    Unknown value.

**LevelAmbient** (`Vector`_)
    Unknown value.

**LevelBackAmbient** (`Vector`_)
    Unknown value.

**LastLoadedTerritory[64]** (`char`_)
    Unknown value.

**MaxWorldObjects** (`int`_)
    Unknown value.

**AllObjects** (`Rfg::BaseArray<Object*>`_)
    Unknown value.

**TechLevel** (`float`_)
    Unknown value.

**TechLevelMax** (`float`_)
    Unknown value.

**FlaggedObjects** (`Object*`_)
    Unknown value.

**CurrentFlaggedObject** (`Object*`_)
    Unknown value.

**CurrentFlaggedMode** (`char`_)
    Unknown value.

**DeserializeList[144]** (`char`_)
    Unknown value.

**CurWorldState** (`WorldStateMode`_)
    Unknown value.

**SlFlags** (`SaveLoadInfo`_)
    Unknown value.

**PendingGameSaveSlot** (`GameSaveInfo*`_)
    Unknown value.

**DlcBundleId** (`int`_)
    Unknown value.

**PendingFilename[64]** (`char`_)
    Unknown value.

**PendingGameLoadWarpToPos** (`Vector`_)
    Unknown value.

**PendingGameLoadWarpToOrient** (`Matrix`_)
    Unknown value.

**Grid** (`StreamGrid*`_)
    Unknown value.

**StreamPos** (`Vector`_)
    Unknown value.

**NumTerritoryZones** (`int`_)
    Unknown value.

**GlobalZoneGrid[257]** (`WorldZone*`_)
    Unknown value.

**IsTerritory** (`bool`_)
    Unknown value.

**TerritoryName[128]** (`char`_)
    Unknown value.

**NumStreamingObjects** (`int`_)
    Unknown value.

**StubSerializationInProgress** (`bool`_)
    Unknown value.

.. _`bool`: ./PrimitiveTypes.html
.. _`Vector`: ./Vector.html
.. _`char`: ./PrimitiveTypes.html
.. _`int`: ./PrimitiveTypes.html
.. _`Rfg::BaseArray<Object*>`: ./Rfg::BaseArray<Object*>.html
.. _`float`: ./PrimitiveTypes.html
.. _`Object*`: ./Object*.html
.. _`WorldStateMode`: ./WorldStateMode.html
.. _`SaveLoadInfo`: ./SaveLoadInfo.html
.. _`GameSaveInfo*`: ./GameSaveInfo*.html
.. _`Matrix`: ./Matrix.html
.. _`StreamGrid*`: ./StreamGrid*.html
.. _`WorldZone*`: ./WorldZone*.html
