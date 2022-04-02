---
permalink: /railverse/api/vector
title: "Lua Documentation"
toc: true
---

## Vector

### Inheritance Hierarchy
- **Vector**

### Syntax
```lua
class "Vector"
```

### Remarks
A vector in 3-D space composed of components (X, Y, Z) with double floating point precision.

### Variables
| Name | Type | Description | Notes |
|:-----|:-----|:------------|:------|
| X | Number | Vector's X Component ||
| Y | Number | Vector's Y Component ||
| Z | Number | Vector's Z Component ||

### Constructors

| Name | Description | Notes |
|:-----|:------------|:------|
| ``` new "Vector"()``` | Default Constructor |  
| ``` new "Vector"(I : Number)``` | Constructs a vector with all components equal to ``I`` | 
| ``` new "Vector"(X : Number, Y : Number, Z : Number)``` | Constructor using initial values for each component. | 

### Methods

| Method | Arguments | Description |
|:-------|:----------|:------------|
|  | | |

### Operators

| Name | Output | Description | Notes |
|:-----|:-------|:------------|:------|
| ``` __add(self, other : Vector)``` | Vector |Gets the result of component-wise addition of self and another vector |  
| ``` __sub(self, other : Vector)``` | Vector |Gets the result of component-wise subtraction of self and another vector | 
| ``` __mul(self, other : Vector)``` | Vector |Gets the result of component-wise multiplication of self and another vector | 
| ``` __div(self, other : Vector)``` | Vector |Gets the result of component-wise division of self and another vector | 
| ``` __eq(self, other : Vector)``` | Boolean | Checks against another vector for equality | 
| ``` __tostring(self)``` | String | Get a textual representation of this vector. |