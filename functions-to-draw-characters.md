###Functions to Draw Characters

In the first project, students wrote a sequence of code statements to draw and color shape primitives to create a 2D character.  In order to improve our code, we want to make it more modular - so we'll break down our code logic into functions.

In addition, we'll use the processing transform functions to translate the origin to our character's center point, as a first step in thinking about how we'll eventually animate the character.

###Example:  Turtle 
In the following description, we'll look at how to write code to create a simple turtle - using functions to specify the overall turtle's design, with additional functions that define the subcomponents of the turtle, like the head or feet.

[Example: Khan Academy Code - Turtle Character](https://www.khanacademy.org/computer-programming/turtle/5949969377984512)


DrawTurtle Logic:

```java

///bodyX, bodyY determine character position
var drawTurtle = function(  bodyX, bodyY, headAngle, footAngle){
    pushMatrix();
    translate( bodyX, bodyY);
    
    drawHead( 91,-22,headAngle);
    drawFoot(37,23, footAngle); //front foot
    drawFoot(-38,23, footAngle); //back foot
    ///Draw the turtle body
    fill(0, 255, 55);
    ellipse( 0,-18,189,99);
    
    
   //center: (0,0), draw point of rotation
    fill(255, 0, 0);//red 
    ellipse( 0,0,5,5);
    popMatrix();
};  

```