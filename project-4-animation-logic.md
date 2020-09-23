# Project 4 - Animation Logic

Project 4 - Animation

## Animation Based on Finite State Machine Logic

The example programs below give simplified examples of animation that is controlled using an animation `state` variable and an animation `position` variable to control the animation.

### Simple Rotate Animation

In the example project below, a rotate animation is controlled by a State Variable: `rotateState` which can be in one of 3 possible states: "UP", "DOWN", or "STOP".

This rotateState variable provides logic to control the animation using a [finite state machine](finite-state-machine.md) structure.

Example Khan Academy Programs:

Rotate Animation: [https://www.khanacademy.org/computer-programming/simpleanimation/6670336845873152](https://www.khanacademy.org/computer-programming/simpleanimation/6670336845873152)

**Animation state variable: rotateState:** can be in one of 3 possible animation states: "UP", "DOWN", or "STOP"

**Animations position variable: angle.**

* When in "UP" state, angle is incremented: angle++
* When in "DOWN" state, angle is decremented: angle--
* `angle` is restricted to range of values between minAngle and maxAngle.

**Animation events:**

* When the `angle >= maxAngle`, then the animation state: rotateState is set to: "DOWN"
* When `angle <= minAngle`, then animation state: rotateState is set to: "UP" 
* When the count variable equals maxCount, rotateState is set to: "STOP" to stop the animation.

**Animation of line and offset rectangle** ![](.gitbook/assets/Screenshot%202017-11-10%2008.07.46.png)

```java
//Global variables:

var rotateState = "UP"; //"DOWN" , "STOP"
var angle = 13;
var maxAngle = 45; //boundry conditions
var minAngle = -45; //boundry conditions
var count = 0;
var maxCount = 5;

//draws a rectangle at points: x,y
//with rotation: offsetAngle
//draws small ellipse at rotation point
var rotateRect = function( x, y, offsetAngle){
    pushMatrix();
    translate( x,y);
    rotate( offsetAngle);
    fill(255, 247, 0 );//yellow
    rect(0,0,50, 90);
    //draw ellipse at rotation point
    ellipse(0,0,10,10);
    popMatrix();
};

//draws a line at x,y
//rotate the line by: lineAngle
//draws an ellipse at rotation point
//calls rotateRectangle to create a //dependent, child-rectangle that rotates //relative to the parent line's rotation  
var drawLine= function(  x, y, lineAngle)
{
    pushMatrix();
    translate(x,y);
    rotate( lineAngle);
    stroke(255, 0, 0);
    strokeWeight(5);
    line( 0,0,100,0);
    //draw offset rectangle that has relative rotation of 40
    rotateRect( 81,1, lineAngle-40);
    //draw ellipse at rotation point: 0,0
    ellipse( 0,0,10,10);
    popMatrix();
};

var checkAngle = function( ){
    if( rotateState === "UP"){
        angle ++;
        if( angle > maxAngle) { //event happened
            rotateState = "DOWN";
        }
    }
    else if( rotateState ==="DOWN"){
        angle--;
        if( angle < minAngle ){
            rotateState = "UP";
            count++;
            println("count " + count);
        }
    }
};

var checkCount = function( ){
    if(count > maxCount){
        rotateState ="STOP";
    }
};

var draw = function() {
  background(255);
  //negative value for angle value 
  //is used so that up-movement is positive rotation
  //down-movement is negative rotation
  drawLine( 200,150, -angle);
  checkAngle ();
  checkCount();
};
```

### Additional Simplified Animation Examples

[https://www.khanacademy.org/computer-programming/animation-demo-simple/5581835098324992](https://www.khanacademy.org/computer-programming/animation-demo-simple/5581835098324992)

[https://www.khanacademy.org/computer-programming/simple-rotateanimation/6227637252587520](https://www.khanacademy.org/computer-programming/simple-rotateanimation/6227637252587520)

