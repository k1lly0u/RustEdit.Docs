---
title: RustEdit Extension
---

The RustEdit extension expands our capabilities of what we can achieve in custom maps. The extension requires that you have Oxide or Carbon installed on your server

Current features of the extension are
- Establishes IO connections made in the editor
- Populates custom loot containers and ensures they respawn/refresh loot at the rates set in the associated loot profile
- Creates spawn handlers for all loot containers placed in the editor without a loot profile so they respawn/refresh loot at default rates
- Creates spawn handlers for all resource entities placed in the editor so manually placed resources will respawn
- Populates custom vending machines using the vending profile associated with it
- Overrides OceanPatrolPath generation with a custom path created in the editor
- Fixes the spawn point prefab and ensures players will only spawn on them

The extension updates itself automatically when a new version is released

So to make use of the IO tools, the custom Loot/Vending machine etc you must have this extension installed!

You can download the extension [here](https://github.com/k1lly0u/Oxide.Ext.RustEdit/raw/master/Oxide.Ext.RustEdit.dll)

To install the extension, copy the Oxide.Ext.RustEdit.dll to your /serverroot/RustDedicated_Data/Managed/ folder and restart your server
