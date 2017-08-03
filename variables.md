# Variables

**Variables** 
Variables provide a way for us to store a value that we can modify and use throughout a program.

Variables 

A variables can be considered a named memory container where the programmer can store values that will be changing in their programs.

To create a variable, we use the keyword **var**, followed by the name that we'll use as a label to access that value.

  var mySpecialValue;  //declare a variable  

This _varible-name_ acts as a label to identify an area in the computer's memory where the value will be stored, so the programmer can access and modify the value throughout the program. 

**Declare and initialize a variable:**

```java
var mySpecialValue;  //declare a variable
    mySpecialValue=5;  //assign a value of 5
    mySpecialValue = 15 * 2; //re-assign a new value to the variable
```

The code above creates a variable by declaring the keyword: var, followed by the identifier name  `mySpecialValue`. In the next statement, we assigns the value 5 to the variable. The third line of code changes the value stored in the memory location: `mySpecialValue`  to the result of the evaluation of the expression: 15 \* 2.

### Variable Types

Javascript in a **loosely-typed** programming language. The type of a variable is determined dynamically, based on the value currently assigned to the variable.  A variable can be assigned different types of values throughout a program. This is in contrast to most other programming languages like Java or C++, which are **strongly-typed**.  In **strongly-typed** languages, when we want to declare a variable, we must first specify the **data-type** that we want to use.

* Variable Types:   
* 
### Dynamically Determined Variable Type

```java
var mySpecialValue = 5;   //assigned a numeric type
mySpecialValue="hello";   //a string has now been assigned to the same variable
```



