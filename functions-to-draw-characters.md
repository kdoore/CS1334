###Functions to Draw Characters

In the first project, students wrote a sequence of code statements to draw and color shape primitives to create a 2D character.  In order to improve our code, we want to make it more modular - so we'll break down our code logic into functions.

In addition, we'll use the processing transform functions to translate the origin to our character's center point, as a first step in thinking about how we'll eventually animate the character.

###Example:  Turtle 
In the following description, we'll look at how to write code to create a simple turtle - using functions to specify the overall turtle's design, with additional functions that define the subcomponents of the turtle, like the head or feet.

[Example 1:  Turtle in a Single Javascript Function ](https://www.khanacademy.org/computer-programming/turtle_version1/6054458239942656)

[Example 2:  Turtle using multiple functions](https://www.khanacademy.org/computer-programming/turtle/5949969377984512)


DrawTurtle Logic: 
The code below is the main function to create the  turtle. Within this function, other functions are called to create his sub-components.  The subcomponents, like feet and head have a dependency on the turtle body, whenever the body moves, the head and feet should also move.  This dependency is implemented by calling the drawHead, drawFoot functions after translate( x,y) has moved the origin to the turtle's center point.

```java

///bodyX, bodyY determine character position
var drawTurtle = function(  bodyX, bodyY, headAngle, footAngle){
    pushMatrix();
    translate( bodyX, bodyY);
    
    drawHead( 91,-22,headAngle); //draw before main body
    drawFoot(37,23, footAngle); //front foot
    drawFoot(-38,23, footAngle); //back foot
    
    ///Draw the turtle body shapes
    fill(0, 255, 55);
    ellipse( 0,-18,189,99);
    
   //center: (0,0), draw point of rotation
    fill(255, 0, 0);//red 
    ellipse( 0,0,5,5);
    popMatrix();
};  

```

###Calling the drawTurtle Function
The code below shows how to call the drawTurtle function within the Processing draw( ) function by passing in parameter values that have been declared as global variables.  Eventually, we'll be able to animate the turtle by modifying the value of these global variables in the draw loop.

We can see that the animation variables are passed directly into the drawTurtle function, then they will be passed into each of the functions where they are controlling animation.

```java


///GLOBAL VARIABLES
{
var bodyX=152;
var bodyY=250;
var headAngle=0;
var footAngle = 8;
}

var draw= function() {
  background(255, 255, 255);
  drawTurtle(bodyX, bodyY,headAngle, footAngle);   

};

```

###DrawHead( ) and DrawFoot functions

```java
//drawHead - headX, headY control position relative to the turtle body
//headAngle - tilts the head at the rotation point
var drawHead=function( headX, headY,headAngle ){
    pushMatrix();
    translate( headX, headY);
    fill(183, 255, 0);//light green
    rotate(headAngle); //rotate the head
    ellipse( 16,-3,52,33);///draw head offset from the origin
    fill(5, 5, 5);  //black
    ellipse(15,-7,10,10); //eye
    
  //center: (0,0), point of rotation
    fill(255, 0, 0);//red
    ellipse( 0,0,5,5);
    popMatrix();
};


//drawFoot, called from within drawTurtle
//footX, footY control position relative to the turtle body
//rotation occurs at point: footX, footY
//center of foot ellipse is drawn offset from footX, footY 
var drawFoot = function( footX, footY, footAngle){
    pushMatrix();
    translate( footX, footY);//move origin to foot position
    rotate( footAngle);
    fill(183, 255, 0);//light green
    ellipse(0,16, 33,58); //foot with ellipse offset from 0,0
    
   //center: (0,0), point of rotation
    fill(255, 0, 0);//red
    ellipse( 0,0,5,5);
    popMatrix();
};




```