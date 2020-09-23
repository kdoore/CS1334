# Collision between objects

When we want to animate objects colliding, we need to consider the geometry of each object, and determine when the object geometry overlaps. For this example, we'll look at collision between an ellipse and a rectangle.

Example Khan Academy Project:

[https://www.khanacademy.org/computer-programming/colliding-objects/5192472599134208](https://www.khanacademy.org/computer-programming/colliding-objects/5192472599134208)

## Object Geometry

The image below shows the geometry for the 2 objects used in this example. We have a ball object and a target object. The ball object is defined by the following:

```text
center:  bX, bY
radius: bR  
diameter: 2 * bR
```

The target is a rectangle defined by the following:

```text
upper-left point: tX, tY
width: tW
height: tH
```

As seen in the image below, the geometries overlap on the left edge of the rectangle when the following is true: bX + bR &gt; tX //the right edge of the ball \(bX + bR\) is greater than than the left edge of the target \( tX \);

![](.gitbook/assets/Screenshot%202017-11-15%2012.59.48.png)

## Functions to Draw Objects

We'll create simple functions to create modular logic for this project. We'll have functions to draw the objects, and an additional function to test for collision between the objects. Collision implies that we have moving objects, so we'll need to have: global variables for position and speed of the objects, since those values will be changing. We will also create variables for the geometry: radius, width, and height of the objects to allow us to determine if we have collision.

```java
var drawBall = function( bX, bY, bR )
{
    fill(255, 0, 0); //red
    var bD = 2 * bR;  //ball diameter is used to draw ellipses
    ellipse( bX, bY, bD, bD);
};

var drawTarget = function( tX, tY, tW, tH){
   fill(0, 153, 255); //blue
    rect( tX, tY, tW, tH);
};
```

## KeyPress to move the target:

In the draw function, we'll check if any keyIsPressed, and then check to see if the current keyCode is UP or DOWN.

```java
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
```

## Check Collision

//parameters: we need to pass in all object geometry to test for collision

```java
var checkCollision = function( bX, bY, bR, tX, tY, tW, tH)
{
   var isColliding = false; //assume no collision as default
   //Conditions where ball intersects with edges of the target

   var leftEdgeCondition = (bX + bR) > tX;        //rt edge of ball
   var rightEdgeCondition = (bX - bR) < tX + tW;  //left edge of ball
   var topEdgeCondition = (bY + bR) > tY;         //bottom edge of ball
   var bottomEdgeCondition = (bY - bR) < tY + tH; //top edge of ball

    //All conditions must be true for intersection / collision to occur
   if( leftEdgeCondition && rightEdgeCondition && topEdgeCondition && bottomEdgeCondition){
       isColliding = true; //change return value to true
     //  println("Colliding");
   }
   return isColliding; //return result of calculation: true or false
};
```

## Animating the Ball

In this example, the ball's animation is that it bounces between the left and right edges of the canvas, it also bounces off the target if collision has occurred. Animation can be controlled using a variable for speed, where the speed is reversed when collisions occur.

In this example, this code is written directly in the draw loop.

Here's the full code for the draw function:

* check for keyPressed to change the value of targetY.  
* check for ball hitting either wall - reverse speed
* check for collision with target - reverse speed
* update ball's position by adding speed
* draw Ball
* draw Target

```java
var draw= function() {
    background(200);
    //change target position if up or down arrows are being pressed
     if(keyIsPressed){
        if( key.code === CODED){
            if(keyCode === UP){
                targetY--;
            }
            else if(keyCode === DOWN){
                targetY++;
            }
        }
    }// end check for keyIsPressed

    //Check for Collisions - if collision occurs, reverse ball speed
     //check for collision with walls
    if( ballX > 400 || ballX < 0){
       bSpeed *= -1;
    }
     //check for collision with target 
    var targetCollision = checkCollision( ballX, ballY, ballR, targetX, targetY, targetW, targetH);
    if( targetCollision ){
        bSpeed *= -1;
    }

    ballX += bSpeed;  //change ball position by adding speed

    //draw both objects
    drawBall(ballX, ballY, ballR);
    drawTarget( targetX, targetY, targetW, targetH);
};
```

