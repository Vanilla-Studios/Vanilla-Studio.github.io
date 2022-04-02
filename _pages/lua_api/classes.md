---
permalink: /railverse/api/classes
title: "Lua Documentation"
toc: true
---

## Getting started
Railverse uses a custom class system for lua.

### Declaring a class
To create a class, use the global ``class`` keyword followed by the classes name and a table. An example can be seen below:
```lua
class "example" {

}
```
### Declaring a class method
To create a class method, create an anonomous function inside the class table. The ``self`` keyword **must** be passed in as the first argument. An example can be seen below:
```lua
class "example" {

    -- Declared method
    exampleFunction = function(self)
        -- Do stuff
    end

}
```
### Declaring the class constructor
Declaring the class constructor is similar to declaring a class method. To declare a constructor, simply declare a method with the name ``init``. An example can be seen below:
```lua
class "example" {

    -- Class constructor
    init = function(self)
        -- Do stuff
    end
}
```
### Inheriting another class
By default, all classes inherit a base ``Object`` class. However, this can be overridden. To overide, declare the name of the parent class at the first index of the class table. An example can be seen below:
```lua
class "example" { "Mod" -- Declaring the mod class as the parent


}
```

### Creating an instance of your class
Creating an instance of your class is similar to methods in Java, C# or even C++. To create an instance, use the ``new`` keyword followed by the name of the class and parenthesese containing the constructor arguments. An example can be seen below:
```lua
local Instance = new "example"()
```

### Calling a instance method
An example can be seen below:
```lua
local Instance = new "example"()

Instance:exampleFunction();
```

<!-- # Mod Class

### Variables

| Name | Type | Description | Notes |
|:-----|:-----|:------------|:------|
| Name | String |The name of the mod. | This variable must be assigned by the developers. |
| Authors | String Table | The authors of the mod. | This variable must be assigned by the developers.

### Methods

| Method | Arguments | Description |
|:-------|:----------|:------------|
| Mod#addGlobalScript | {::nomarkdown}<div><ul> <li> GlobalValue : String </li><li>ReletiveFilePath : String</li></ul></div>{:/}| Adds script to global registry that can be accessed easily by other mods. |

### Implementable methods

| Method | Description |
|:-------|:------------|
| Mod#Load | Called when the mod is loaded |
| Mod#Unload | Called when the mod is unloaded  -->

---
# Important links

[Vector Class](https://vanillastudios.co.uk/railverse/api/vector)