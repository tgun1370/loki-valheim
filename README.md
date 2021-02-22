
Works for Valheim 0.145.6 (2021-02-16)

## Use

- Grab and extract to game directory: https://mega.nz/file/0UAlxQwK#47InGOb8ViI6GyBDArpbhkbMTBklXdyRSmAc4-BZpJY
- Copy the mod DLLs that you want into `BepInEx\plugins`
- Run the game!
- After running the game at least once, navigate to `BepInEx\config` to edit mod configurations
- Run the game again!

## Current mods

Please note that client mods should work on online servers as well, so respect the server rules and don't ruin the game for your friends

- Autopickup filter: Cycles between 3 modes when pressing L (accept all, block trash, block all) and has a customizable trash list in the config tailored for the endgame. Items won't be picked up automatically if blocked, but can still be picked up manually.
- Death announcer: When a player dies, it is announced to every other player
- First Person mode: Allows you to play the game in first person. Press H to cycle between third person, first person with helmet, and first person without helmet. Has some additional configuration options
  - Known issue: the helmet mode shows a graphical artifact near your mouth. There's an experimental fix that reduces this problem but the fix negatively affects some helmets as well
  - Known issue: Nearby grass disappears
- Immersion mode: Aims to make the game more immersive
  - Removes the map and minimap (Ctrl+O to toggle)
  - Allows constructing wooden buildings without a workbench nearby so you can build signposts easily, which you will need when you don't have any map available!
  - more to come
- Repair items anywhere: Press U to repair everything anywhere
- Stamina mod: Allows you to configure stamina regeneration and the usage modifier

## Developers

Start by following the plugin setup for Bepinex:
- https://bepinex.github.io/bepinex_docs/master/articles/dev_guide/plugin_tutorial/index.html

Valheim seems to be using mscorlib.dll 4.6.57.0 (.Net Framework 4.6)

Follow the DLL lib copying instructions in the above "Getting Started", and copy them all to `Libs\`
- All `assembly_*.dll` files from `<VALHEIM_DIR>\valheim_Data\Managed`
- UnityEngine.dll (and UnityEngine.CoreModule.dll if needed): `<VALHEIM_DIR>\valheim_Data\Managed`
- BepInEx & Harmony DLLs (see above link): 0Harmony.dll, BepInEx.Harmony.dll, BepInEx.dll

### Starting a new mod

Read: https://bepinex.github.io/bepinex_docs/master/articles/dev_guide/plugin_tutorial/2_plugin_start.html
(I.e. create a new project, reference everything under `Libs\`, and start with BaseUnityPlugin + [BepInPlugin]`. See ExampleValheimMod.)
(or use this template: https://github.com/BepInEx/BepInEx.PluginTemplate)

Reference work:
- HarmonyX: https://bepinex.github.io/bepinex_docs/master/articles/dev_guide/runtime_patching.html
- General approach to finding out what to patch, etc: https://bepinex.github.io/bepinex_docs/master/articles/dev_guide/dev_tools.html
