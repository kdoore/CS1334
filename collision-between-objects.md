#Collision between Objects

When we want to animate objects colliding, we need to consider the geometry of each object, and determine when the object geometry overlaps.  For this example, we'll look at collision between an ellipse and a rectangle.

Example Khan Academy Project:

[https://www.khanacademy.org/computer-programming/colliding-objects/5192472599134208](https://www.khanacademy.org/computer-programming/colliding-objects/5192472599134208)

###Object Geometry
The image below shows the geometry for the 2 objects used in this example.  We have a ball object and a target object.  The ball object is defined by the following: 

    center:  bX, bY
    radius: bR  
    diameter: 2 * bR

The target is a rectangle defined by the following:

    upper-left point: tX, tY
    width: tW
    height: tH

As seen in the image below, the geometries overlap on the left edge of the rectangle when the following is true: 
    bX + bR > tX  //the right edge of the ball is larger than the left edge of the target
    
![](/assets/Screenshot 2017-11-15 12.59.48.png)

###Functions to Draw Objects
We'll create simple functions to create modular logic for this project.  We'll have functions to draw the objects, and an additional function to test for collision between the objects.  Collision implies that we have moving objects, so we'll need to have: global variables for position and speed of the objects, since those values will be changing.  We will also create variables for the geometry: radius, width, and height of the objects to allow us to determine if we have collision.

var drawBall = function( bX, bY, bR){


}


###Key Press to move the target:
In the draw function, we'll check if any keyIsPressed, and then check to see if the current keyCode is UP or DOWN.
var draw = function(){
background(255) //draw white bkground
 
 if(keyIsPressed){
        if( key.code === CODED){
            if(keyCode === UP){
                targetY--;
            }
            else if(keyCode === DOWN){
                targetY++;
            }
        }
    }
//other code
}

