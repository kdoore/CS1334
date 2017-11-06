#Arrays

Arrays are a data-structure that can be used store multiple variable values. 

Example Khan Program that uses Arrays for Animation

https://www.khanacademy.org/computer-programming/arrays-bouncing-balls/6637063593721856

###Arrays are Objects
Arrays are objects in javascript, this means that arrays have properties and functions that the array object can use.  

###Declare and Initialize Arrays
There are several methods to initialize arrays, one method creates an empty array, where empty square brackets indicate an Array type variable is created.  The second method to declare and initailize an array is to put values within the square brackets when declaring the variable.  
Bracket notation is used when working with arrays.  

    var myElements = [ ];  //declare an empty array
    
    var myElements2 = [ 1, 2, 5 ]; // an array with 3 elements

###Bracket Notation
Square Brackets are used to initialize and modify arrays and array elements.  

1.  When declaring an array, a list of comma-separated values within the brackets are used to set values for individual array elements. 
2.  After the array has been initialized, only integer values can be used within the array brackets, the integer is called the array index and it indicates the order or position of each array element within the array's list-like structure. In the examples below, the first element in the Array can be accessed using the index value: 0.  Array elements have index values start at 0 and must be integer, whole numbers.

    a.  Set a value
        myElements[0] = "hello";
        
    b.  Get a value
        var msg  = myElements[0];  // get the first element

###Dot Notation
Since Arrays are objects, each time we create an array we can use all of the code features that are included in the array class definition.  To find out how to work with arrays, we can look at the Javascript documentation:  

[Array Documentation -  MDN Javascript Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

```java
var myElements = [ 1,5,7,9 ];
var size = myElements.length; //access length property
myElements.push( 11 ); //new element added as 5th item
myElements[4] = 0; //modify the last element added
```

###Length Property
Array's have a `length` property, which stores the number of elements in the array.  This is determined by the position of the last item in the array.  An array can have a large length, yet not have valid data in each array element.  

###push( ) Method
Arrays can use the push( ) method to safely add new elements to the end of the array.