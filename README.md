# RFGR Script Loader Wiki
  RFGR Script Loader is a scripting interface for Red Faction Guerrilla Re-mars-tered edition. Using LuaJIT 2.0.5 as the scripting language. This repo is used to provide public information about the project while keeping the source private. 

### Project goals
  Normally, modding RFGR involves editing xtbl files which are simply xml files with a different extension. The problem with this method is that there are many hardcoded values in the xtbl files meaning modders are limited on what they can change. This tool aims to bypass the normal limitations of modding the game by allowing modders to change many hardcoded values and giving them access power and flexibility which a scripting language allows for.

  Of course, first an interface between the games structures and the scripts must be created. As of now the project is still very early on and few things are accesible to the scripts. The scripting interface will need to be expanded, and ways to easily control the scripts must be added. Another goal would be to provide debugging interfaces within the game. Hopefully allowing them to view the inner state of the game as it runs and also examine individual objects in the game world and their state. This page will be updated as more features are added.

### Usage
1) Download the latest release from the [releases](https://github.com/Moneyl/RFGR-Script-Loader-Wiki/releases) page.
2) Unzip the release and copy the folder it contains into your Red Faction Guerrilla Re-mars-tered folder. In steam you can find that by right clicking the game in your library, clicking properties, the local files tab, and then the "Browse local files" button. Once unpacked, you should see the script loader at "../Red Faction Guerrilla Re-MARS-tered/RFGR Script Loader/RFGR Script Loader.exe".
3) Next, run RFGR Script Loader.exe as admin. You may run it while the game is running or while it isn't. If the game isn't running it will autostart it by default. Now, you must wait for 3 beeps to sound off. If you hear them that means it has successfully loaded into RFGR. If you ran it from startup you may need to wait until the main menu for this to occur. 
4) You can use F1 to toggle the overlay, Numpad 1 to turn the HUD and fog off, and Numpad 2 to turn them on. The "Main Overlay" window won't be usable until you load a save. The first time you open it must be with the game unpaused, but after that it will work in the pause menu. This limitation will be fixed in time. 
5) From here you can use some useful functions such as invulnerability, infinite jetpack, and teleports. This release (0.02) does not feature scripting and was intended to test out the overlay and root out any bugs early.
6) Once scripting is added, I will expand the [wiki](https://github.com/Moneyl/RFGR-Script-Loader-Wiki/wiki) with some tutorials, examples, and lua function documentation.

### Roadmap

### Gallery

### Why is this closed source?
  One of my primary concerns with this project being open source is that people will use it to cheat in the MP mode of the game. While the MP mode isn't as active as it used to be, I'd still hate for it to be ruined for everyone. There are many checks which will crash the game if the player enters MP mode while the script loader is active. If the source was public then it would be trivial to remove those checks from the code and use it as a cheating tool.
