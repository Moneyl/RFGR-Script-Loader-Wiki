# RFGR Script Loader Wiki
  RFGR Script Loader is a scripting interface for Red Faction Guerrilla Re-mars-tered edition. Using LuaJIT 2.0.5 as the scripting language. This repo is used to provide public information about the project while keeping the source private. 

## Project goal
  Normally, modding RFGR involves editing xtbl files which are simply xml files with a different extension. The problem with this method is that there are many hardcoded values in the xtbl files meaning modders are limited on what they can change. This tool aims to bypass the normal limitations of modding the game by allowing modders to change many hardcoded values and giving them access power and flexibility which a scripting language allows for.

Of course, first an interface between the games structures and the scripts must be created. As of now the project is still very early on and few things are accesible to the scripts. The scripting interface will need to be expanded, and ways to easily control the scripts must be added. Another goal would be to provide debugging interfaces within the game. Hopefully allowing them to view the inner state of the game as it runs and also examine individual objects in the game world and their state. This page will be updated as more features are added.

## Why isn't this project open source
  One of my primary concerns with this project being open source is that people will use it to cheat in the MP mode of the game. Yes, the MP mode isn't as active as it used to be, but I'd hate for it to be ruined for everyone. There are many checks which will crash the game if the player enters MP mode while the script loader is active. If the source was public then it would be trivial to remove those checks from the code and use it as a cheating tool.
