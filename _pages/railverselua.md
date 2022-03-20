---
permalink: /railverse/api
title: "Lua Documentation"
---

# Mod.lua

## Functions

 
| Method | Arguments | Description |
|--------|-----------|-------------|
| Mod#addGlobalScript | <ul> <li> GlobalValue : String <li>ReletiveFilePath : String </ul> | Adds script to global registry that can be accessed easily by other mods |

## Implementable methods

| Method | Description |
|--------|-------------|
| Mod#Load | Called when the mod is loaded |
| Mod#Unload | Called when the mod is unloaded 