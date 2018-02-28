#Canvas Border Constraints for Animation

Bounding Ball programs are a classic approach to learning how to work with constraints.  We want to make sure that when the ball hits a canvas border that we have logic to change the ball's direction.

This case is different than the button constraints, in the button situation we wanted to test if the mouse was within a rectangular space. To insure that the mouse was within the box, it was required that **all bounddry-conditions were true** when we compared the mouseX to the left and right sides of the box, and when we compared mouseY to the upper and lower edges of the button rectangle.  In this case, if any of the conditions are true, then we need to change the ball's speed.  It may be beneficial in this case not to have 1 large boolean expression, because we may want to do different actions when the ball intersects with the left, right walls, as compared to when it intersects with the floor and ceiling.  So, in this case, we can setup one if statement for the case when the ball hits the ceiling, and a different case when it hits the floor.  

 Initial conditions - we need to be careful defining our initial starting values for the ball's position, if the ball's initial position is already outside the boundary that we're testing for collision with, we may have the ball get stuck. Similarly, when intersection happens, we may need to move the ball outside the test region, just so it doesn't get stuck in a state where each frame it's speed changes direction, and it's hovering, stuck in limbo.  
 
###Simple Object Movement
We can consider simple object movement in terms of position and speed. Acceleration can be included for a slightly more sophisticated approach.

###Position and Speed
The ball object has variables: ballX, ballY which store the values of it's position at any time.  For simple movement, we can simply increment position values during each execution of the draw( ) function.

ballX += 1;  //simplest case, update position with a constant value

ballX += speed;  //create a variable, speed to keep track of the ball's speed

###Collision Condition - Hitting a canvas boundary
In the 1 dimensional case, where we're just focused on the object's x-position and horizontal movement, we can try to keep the ball within the canvas.  This involves 2 steps:
 1. determining if the ball has left the canvas area
 2. deciding what action to take if that has happened
 
We want to add conditional logic to our program, first, let's assume the ball starts on the left side, moves to the right, and we want to determine when it has hit the right border.  Once it's hit the border, we can either get it to reverse direction or we can move the ball back to the left edge of the screen.

1. Test for collision with right border:

###Move ball back to the left edge
```java
var speed = 5;  //positive speed will move ball in positive x direction
// move ball back to left edge
if ( ballX > width){   //canvas width = 400
 ballX = 0; //move ball back to left edge
}
ballX += speed;  //update the ball's position by adding speed
```

###Bounce-off Right Border
```java

//bounce off right-border, reverse speed value
if ( ballX > width){   //canvas width = 400
 speed = -5;  // we can make speed negative
}
ballX += speed;  //update the ball's position, negative speed will move ball to the left, positive speed moves ball to the right
```

###Check Both Left and Right Borders Independently - Consider Ball Size
At any one point in time, the ball is only in one location, but we should check each frame to see if it's new position is now at one of the left or right edges.  If either of these situations is true, we will want to change the value of speed, this is the action that we want to take, this code will go inside the if-statement statement code block.  We can be more specific with our test, where we now look to see if the edge of the ball has intersected with the canvas wall boundaries.

```java

if( ballX > width-radius){  // ball edge at right border
    speed = -5;  //make speed negative
}

if( ballX < 0 + radius){  // ball edge at right border
    speed = 5;  //make speed positive
}

```

###Check For Both Walls in 1 Conditional Expression
```java
if( ballX > width-radius || ballX < radius ){
    speed = speed * -1;   //change sign of speed
                         //if positive, make negative, etc
}
```
 
 ![](/assets/Screenshot 2017-10-11 10.21.08.png)

###Example Program with Vertical Acceleration
In the program below, we consider the ball's radius when determining collision with the wall.  This way the ball looks like it's actually bouncing.  Our conditional expressions test to find out when the outer radius of the ball crosses the boundaries, then we take action depending on which border we've intersected with.  These can be individual if statements because we'll take different actions in each situation.  More than one of these conditions may occur at the same time, when the ball hits a corner, so we need to check that our code handles these situations correctly.
 
https://www.khanacademy.org/computer-programming/bouncing-ball/4909833776726016


```java

var ballX = 30;
var ballY  = 25;
var radius = 25;
var speedY = 3;
var speedX = 4;  //constant in x
//var acceleration - we could have a variable for acceleration

//physics of simple object
//position is updated by adding speed each frame
//speed is updated by adding acceleration each frame
//change sign of speed when hitting borders

var drawBall= function(x,y, size){
    fill(255, 0, 0);
    ellipse( x,y,size,size);
};


var draw = function() {
    background( 0);
    
    //draw ball using current ballX, ballY 
    drawBall(ballX,ballY, radius * 2);//pass in x, y, size
  
  //CHECK FOR INTERSECTION WITH BORDERS
  //check position of ball - for intersection with boundaries 
  //if intersection, change direction of speed             
      if( ballX < radius || ballX > width-radius){ //check for impact with left or right border
speedX = speedX * -1 ; //reverse speed on impact
}
    if(  ballY < radius  ){
       speedY = speedY * -1 ;  //reverse speed on impact
       ballY = radius + 1; //reset position outside zone
     }
     if(ballY > height - radius){  //has ball hit the bottom
          speedY = speedY * -1 ;  //reverse speed on impact
          ballY = height-radius-1; //reset position out of impact zone
     }
 //update position
    ballX += speedX;
    ballY += speedY;
 //if using acceleration, here we would also update speed with acceleration  
    
};

```