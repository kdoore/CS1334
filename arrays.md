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


```java
var myElements = [ 1,5,7,9 ];
var size = myElements.length; //access length property
myElements[99]  = 0;
size = myElements.length; //what's the new length?  (100)
```
###push( ) Method
Arrays can use the push( ) method to safely add new elements to the end of the array.

```java
var myElements = [ 1,5,7,9 ];
var size = myElements.length; //access length property
myElements.push( 0); // adds element at end
size = myElements.length; //what's the new length?  (5)
```

###For-Loops to work with Arrays

Since arrays use a numeric index to access each array element, for-loops provide an easy way to access each item in an array.  Loops are often useful when initializing array values.  Loops are used to access each array element to access or modify the value according to your program's logic.

###Initialization Example
In the code example below, 3 arrays are declared and initialized with no elements.  The for-loop initializes 55 elements in the array, where the elements have indexes from 0-54. All of the xPosition elements are set using the loop counter variable i in an expression to offset each value by 25.  All yPosition elements are initialized with a value of 0.  All ySpeed elements are initialized with a random value in the range 1 - 5.


```java
//
var colors = [ ];  
var xPositions = [ ];
var yPositions = [ ];
var ySpeed = [];
var numBalls = 55;  //how many to make

var initializePositions = function( ){
    for( var i = 0; i < numBalls; i++){
      xPositions[ i ] = i * 25;
      yPositions.push(0);
      ySpeed[ i ] = random( 1, 5);
    }
};

//initialize 2 elements in the colors array
colors[ 0 ] = color(255, 0, 89); //red
colors[ 1 ] = color(0, 255, 43); //green


```
###Array Example - For-loop to use array values  
In the code below, a for-loop is used to step through each array element and use the values to create bouncing ball animation because the position values are modified each time the for-loop code is executed in the draw loop.  

```java
//function to draw a single ball using input position values: x, y, and color bColor
 var drawBall = function(  x, y, bColor){
    fill(bColor);
    ellipse( x, y, 10,10);
};   

// Function to animate bouncing balls, yPosition for each ball is updated using ySpeed for each ball.  If the yPosition is at top or bottom of screen, ySpeed is reversed.  Color of balls is determined using modulus, since there are only 2 color elements, modulus insures that each time i is changed, only the values 0, 1 are used to set the ball's color. 
   
var  drawBalls = function(){
////loop to display the balls
for( var i=0; i < xPositions.length; i++){
    var x = xPositions[ i ];
    var curColor = colors[ i % 2 ];
    var y = yPositions[i];
    drawBall( x, y, curColor);
    //test to see if ball hits floor or ceiling
    if( y > 400  || y < 0 ){
        ySpeed[i] *= -1 ; //reverse speed
    }
    yPositions[ i ] += ySpeed [ i ];  //update yPosition values 
 }
};


var draw = function() {
    background(0);
     drawBalls();
};


```

