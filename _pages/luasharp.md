---
permalink: /luasharp/
title: "Lua#"
toc: true
---

LuaSharp (Lua#) is a part of the standard library for Vanilla Studios: Railverse. LuaSharp beter equips lua developers for object oriented programming in Lua.

Lua is a simple to learn language compared to other OOP languages such as Java and C#. LuaSharp aims to implement a simplicar object oriented experience through similar syntax.

___

The examples below will assume that the LuaSharp library is exposed to your script globaly. This is true for all scripts made for Railverse. However, if you are not using this library through Railverse, you will have to download the source code and ``require`` it manually.

## Classes
### Defining a class
In LuaSharp, a class can be declared as such:

```lua
class "Animal" {

}
```

This class has been given the name `animal`. You can give your class any name you desire.

### Defining the constructor
Every class can have a constructor function that is called every time a new instance of the class is created. Creating a new constructor is similar to JavaScript, and can be defined as such.

```lua
class "Animal" {

    -- Make sure to decalre "self" in the arguments of all instance functions.
    constructor = function(self, Arg0, Arg1, ...) -- The constructor can have arguments passed in.
        -- Do something...
    end;

}
```

### Creating a new instance of a class.

Creating an instance of a class is similar to other OOP languages such as JavaScipt, C# and Java. An example can be seen below:
```lua
    local varA = new "Animal"() -- Any arguments declared in the class constructor can be passed here.
```

### Inheritance

Just like in other OOP languages, you are able to borrow behaviours from other classes by extending them. An example of this would be a Wolf inheriting the behaiours of an animal. Because they share most of the same behaviours, you dont need to rewrite all of the code a second time. See below:
```lua

class "Wolf" : extends "Animal" {

    Howl = function(self, Loudness)
        -- Make wolf howl
    end

}

class "Dog" : extends "Wolf" {

    Bark = function(self, Loudness)
        -- Make dog bark
        wait(2)
        self:Howl(Loudness) -- Inheritance allows you to call this from the inherited class.
    end
}
```