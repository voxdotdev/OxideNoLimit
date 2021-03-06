# OxideNoLimit

OxideNoLimit is a Harmony patch for Rust's [Oxide Mod](https://github.com/OxideMod/) which removes the "Sandboxing" from the plugins.  
Rust server has built-in Harmony loader, so all harmony patches (***.dll**) will be hooked up automatically.

  You may need this if:
  - You have plugins that utilizes [Harmony](https://harmony.pardeike.net) library.
  - You want to use things from blacklisted namespaces from plugins.

### Features
  - Completely removes plugin sandboxing.
  - Automatically references the `0Harmony` assembly in plugins.  
  *(No need to include `// Reference: 0Harmony`)*

### Installation
  - Make sure you have **full** access to your server. Don't try to use this on shared/rented servers.
  - Create a directory called `HarmonyMods` in the **root** directory of your Rust server.  
  *(if it is not exists yet)*
  - Put `OxideNoLimit.dll` into `YourServerRootDir/HarmonyMods`.

### Usage Notes
Be careful when doing Unpatch of your Harmony patches!  
Do **NOT** call `UnpatchAll()` on your Harmony instance without specifying the `Instance ID`.  
Doing this will rollback **all** patches been ever made from **all** Harmony instances and will bring back the Sandbox.  
Always explicitly specify your `Instance ID` and [read the docs](https://harmony.pardeike.net/articles/basics.html#unpatching).

--  
  Licensed under MIT. Comes without support & warranties.