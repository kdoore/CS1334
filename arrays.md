#Arrays

Arrays are a ‘data structure’ - a programming construct to store data or information.
Arrays provide methods to store and retrieve values from an ordered list, items are arranged in the list based on the order they are added to the list.
We access an element of the list using the ‘index’  or position value of the item, where array indexes start at 0 and end with the index value: length-1.

Arrays in javascript are `objects`, where objects have behaviors and properties that can be accessed by the actual object instance. 

###Bracket Notation
Brackets are used to create Arrays and to access elements of an Array object instance.  

###Declare and Initialize Array Objects
The examples below show two different ways to initialize an array variable, the first example declares and initializes an empty array, the second example provides 3 values to initialize the array with 3 elements.

    var arrayExample1 = [ ];  //code to declare and initialize array-type variable. 

    //Initialize with data for 3 elements
    var arrayExample2 = [ 1, 4, 5 ];
    var len = arrayExample2.length; // length property
    println("array size: " +  len );  //array size: 3 
    
###Initialize Array Elements




###Dot Notation
Dot notation allows an instance of an object to access it's property values and to call functions or methods associated with the object.  For Arrays, we'll often use the `length` property.  Every instance of an Array object stores it's length in the variable: `length`.  

###Arrays for Animation

[Khan Academy Array Example](https://www.khanacademy.org/computer-programming/arrays-bouncing-balls/6637063593721856)