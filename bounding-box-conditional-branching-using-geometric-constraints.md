#Bounding Box - Conditional Branching using Constraints

When programming interactive visual programs, we often need to check whether certain geometry has overlapping borders.  The simplest case of this is when designing an active area associated with a shape, such as a button, and where we are interested to know if the mouse is positioned over this shape. 

For interaction, we'll assume that we're going to be using multiple functions within our program and that we will need to check variable positions within the draw loop and possibly a mouse event function.  In this siutaion, where we need access to a shape's variables within several processing functions, then we'll need these variables to be global so we can access the variables inside draw( ) and mouseClicked( ).  

We'll create global variables for a button's x,y position and w,h for it's size.
Then, within the mouseClicked( ) function we'll check to see if the mouse position is within each border of the button's rectangular dimensions.  

Khan Example Program for button bounding box
https://www.khanacademy.org/computer-programming/button-bounding-box/5119147397283840

![](/assets/Screenshot 2017-10-10 12.38.15.png)

```java
var x = 100;
var y = 100;
var w = 100;
var h = 50;
var buttonOn = false;  //variable to track the button's state

var drawButton = function(x,y,w,h){
    fill(255, 0, 0); //red is default buttoncolor
    if( buttonOn === true){
        fill(0, 255, 0); //green
    }
    rect(x,y,w,h);
};

var draw = function() {
    background(255);
    drawButton(x,y,w,h );

    //code to draw colored lines and text has been removed
    
};

//check if mouse is within the borders of the box 
//when all of the conditions are true: 
//use && to join multiple conditional expressions

var mouseClicked = function(){
    if( mouseX > x && mouseX < x+w && mouseY > y && mouseY < y + h){
        buttonOn = !buttonOn;  //make buttonOn have opposite truth value, if it was false, turn to true,...if it was true, turn to false 
        println("buttonOn is " + buttonOn); //use println to get debugging information
    }
    
};


```