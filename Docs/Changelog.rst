Changelog
********************************************************

This page contains a list of changes, fixes, and additions made from version 0.4.0 onwards. Changelogs for older version can be found on the `github releases page <https://github.com/Moneyl/RFGR-Script-Loader-Wiki/releases>`_. More details about any changes to scripting or new functions and types can be found in the scripting section of the docs.

v0.4.0
========================================================
Changes
-------------------------------------------------------
- Several dozen new game structs and functions bound to lua. See the scripting section of the docs for more information and example of scripting. This was the primary feature and goal of this release. Writing these docs took up about half of the dev time. Even so, they're incomplete in many places. Contributions are welcome and appreciated. See the `contributing guide`_ for info on how to contribute to the docs.
- Changed the input detection code to something less hacky which should have less issues. The only thing still on the old input system is the script editor shortcuts.
- Added an experimental first person camera, available in the camera settings menu. This is mainly as a proof of concept and to figure out any issues that might come up when making it. The free cam will be bound to lua in a later release so that anybody can perfect it.
- Several additions to the general tweaks menu: AI ignore player, disable player ragdoll, salvage count, ore count, supply crate count.
- Added "High LOD far clip distance" setting to camera menu. For best results set both this and the normal far clip distance setting to higher values (anything above 1200 makes no difference). Increases distance you can see terrain shadows and makes distant terrain look slightly better.
- Added several more error checks when starting the script loader. It will detect some common installation mistakes, warn you about them and shutdown until you've fixed it.
- Inline error markers when you run scripts in the editor
- Syntax highlighting and type tooltip info support in the script editor. Loads type definitions from ``/Settings/LanguageConfig.json``. It has some limitations but will still be useful. I've only added a few types to save time. I'd greatly appreciate if anyone could go through the documentation and add entries for each type and function to this file which I'd include in the next release.
- Added information bar at the top of the script editor that shows info such as line and column number, and what typing mode you're in (insert, caps lock, etc).
- When running scripts through the editor it will now check for syntax errors before running your script, then run it if none are detected. 
- The script editor is now more performant with larger scripts. The colorization code was made more efficient.

Fixes
-------------------------------------------------------
- Fixed weapon lockers and crates freezing the player until reload.
- Attempted a fix on issues surrounding custom explosion spawning. For best results you shouldn't change the "Unique ID" setting.
- Fixed an issue with the script editor not properly adding the ".lua" extension when saving a file for the first time, and added a few checks to prevent accidental overwrites.
- Updated the script editor to fix a bug causing improper cursor placement.

.. _`contributing guide`: ./Contributing.html