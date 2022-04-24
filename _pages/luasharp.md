---
permalink: /luasharp/
title: "Lua#"
toc: true
---

LuaSharp (Lua#) is a part of the standard library for Vanilla Studios: Railverse. LuaSharp beter equips lua developers for object oriented programming in Lua.

Lua is a simple to learn language compared to other OOP languages such as Java and C#. LuaSharp aims to implement a simpilar object oriented experience through similar syntax.

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

    -- Make sure to declare "self" in the arguments of all instance functions.
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

### Class Inheritance

Just like in other OOP languages, you are able to borrow behaviours from other classes by extending them. An example of this would be a Wolf inheriting the behaiours of an animal. Because they share most of the same behaviours, you dont need to rewrite all of the code a second time. By default, every class inherits a base `Object`. See below:
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

## Structs

### Defining a struct
Defining a structure is similar to a defining a class.
```lua
struct "Person" {

}
```
### Constructing instances

Unlike classes, structs do not have constructors. Instead, structs can define default instance variables that can be assigned when a new instances is created. 
```lua
struct "Person"{
    FirstName = "";
    SecondName = "";

    OtherName = "";

    Age = -1;
}
```

These values can be set when the object instance is created by using the struct "constructor" like so:
```lua
local varA = new "Person"{
    "John"; -- FirstName
    "Smith"; -- LastName
    ""; -- OtherName
    21; -- Age 
}
```
As you can see, creating an instance of a struct is similar to a class.
However, all of the instance variables can be assigned at creation. Alternatively, you dont have to assign the instance variables at creation.
```lua
local varA = new "Person"{}

varA.FirstName = "John"
```
or 
```lua
local varA = new "Person"{
    "John" -- Only declaring FirstName
}

varA.LastName = "Smith"
```

### Struct Inheritance

Like classes, structs can inherit other structs. Note that structs can only inherit other structs and classes can only inherit other classes. The syntax for inheriting other structs is similar to classes:
```lua
struct "Employee" : extends "Person" {

    EmployeeID = -1;
    Salary = -1;
}
```

**Instancing a struct that inherits another has not been finalised. So you should probably stay far from this before I change it and probably break all of your code.**
However, instancing one of these structs only accepts the immediate structs instance variables and not the instance variables from the inherited structs. Example:
```lua
local varA = new "Employee"{
    42069; -- EmployeeID
    21000; -- Salary
}

varA.FirstName = "John" -- Instance variables from inherited classes can still be accessed after the instance has been created.
```

