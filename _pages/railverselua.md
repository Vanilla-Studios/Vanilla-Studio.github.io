---
permalink: /railverse/api
title: "Lua Documentation"
layout: default
---

## Mod.lua

### Variables

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| Name | String |The name of the mod. | This variable must be assigned by the developers. |
| Authors | String Table | The authors of the mod. | This variable must be assigned by the developers.

### Methods

| Method | Arguments | Description |
|--------|-----------|-------------|
| Mod#addGlobalScript | {::nomarkdown}<div><ul> <li> GlobalValue : String </li><li>ReletiveFilePath : String</li></ul></div>{:/}| Adds script to global registry that can be accessed easily by other mods. |

### Implementable methods

| Method | Description |
|--------|-------------|
| Mod#Load | Called when the mod is loaded |
| Mod#Unload | Called when the mod is unloaded 