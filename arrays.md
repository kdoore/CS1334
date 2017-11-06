#Arrays

Arrays are a _data structure_ - a programming construct to store data or information.
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
Once we have declared and initialized our array, we can add elements to the array using bracket notation and the index of the element, or we can use the push( ) method to add elements to the end of the array.

    arrayExample1[0] = 3;  //add an element to the array, initialize with value 3.
    arrayExample1[0] = 5; //modify the value of the first element in the array.

    arrayExample1.push( 6 ); //add a new item to the end of the array

###Dot Notation
Dot notation allows an instance of an object to access it's property values and to call functions or methods associated with the object.  For Arrays, we'll often use the `length` property.  Every instance of an Array object stores it's length in the variable: `length`.  In addition, Array objects can use the `push( )` method to add new items to the array.  Adding an item using the push( ) method results in a new array element being created and the length of the array is increased by one.  The benefit of using the push( ) method is that you don't need to worry about array indexes when adding items to the array, and the length property can be used to determine the newly updated number of elements in the array.

###for-loops with Arrays
for-loops provide a convenient way to work with arrays, the loop control variable can be used as an index to access each array element.  for-loops are useful when initializing elements of array.  for-loops are also useful when accessing array elements to use or modify the values.  The example code below shows both situations:



```
var colors = [ ];  //declare and initiallize an array to hold colors
var xPositions = [ ];
var yPositions = [ ];
var ySpeed = [];
var numBalls = 55;  //how many to make

//initialize each color using bracket notation
colors[ 0 ] = color(255, 0, 89); //red
colors[ 1 ] = color(0, 255, 43); //green


  //use for-loop to initialize array elements
var initializePositions = function( ){
    for( var i = 0; i < numBalls; i++){
      xPositions[ i ] = i * 25;
      yPositions.push(0);  //set all yPositions to 0
      ySpeed[ i ] = random( 1, 5);
    }
};
  
  //function to draw each Ball using array elements for xPosition, yPosition, ySpeed, and 
 var  drawBalls = function(){
////loop to display the balls
for( var i=0; i < xPositions.length; i++){
    var x = xPositions[ i ];
    var curColor = colors[ i % 2 ];  //use modulus to restrict within range of valid colors (0,1)
    var y = yPositions[i];
    drawBall( x, y, curColor);
    //test to see if ball hits floor or ceiling
    if( y > 400  || y < 0 ){
        ySpeed[i] *= -1 ; //reverse speed
    }
    yPositions[ i ] += ySpeed [ i ];  //update yPosition values 
 }
};
  
```



###Arrays for Animation

[Khan Academy Array Example](https://www.khanacademy.org/computer-programming/arrays-bouncing-balls/6637063593721856)