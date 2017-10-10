#Canvas Border Constraints for Animation

Bounding Ball programs are a classic approach to learning how to work with constraints.  We want to make sure that when the ball hits a canvas border that we have logic to change the ball's direction.

This case is different than the button constraints, in that case we wanted to test if the mouse was within a rectangular space, so we had to insure that all conditions were true when we compared the mouseX to the left and right sides of the box, and when we compared mouseY to the upper and lower edges of the button rectangle.  In this case, if any of the conditions are true, then we need to change the ball's speed.  It may be beneficial in this case not to have 1 large boolean expression, because we may want to do different actions when the ball intersects with the left, right walls, as compared to when it intersects with the floor and ceiling.  So, in this case, we can setup one if statement for the case when the ball hits the ceiling, and a different case when it hits the floor.  

 Initial conditions - we need to be careful defining our initial starting values for the ball's position, if the ball's initial position is already outside the boundary that we're testing for collision with, we may have the ball get stuck. Similarly, when intersection happens, we may need to move the ball outside the test region, just so it doesn't get stuck in a state where each frame it's speed changes direction, and it's hovering, stuck in limbo.  

###Example Program 
 
https://www.khanacademy.org/computer-programming/bouncing-ball/4909833776726016


```java

var x  = 30;
var y  = 25;
var radius = 25;
var speedY = 0;
var speedX = 4;  //constant in x
var accelerationY = 0.5;  //like gravity positive downwards


//physics of simple object
//position is updated by adding speed each frame
//speed is updated by adding acceleration each frame
//change sign of speed when hitting borders

var drawBall= function(x,y){
    fill(255, 0, 0);
    ellipse( x,y,radius *2,radius *2);
};


var draw = function() {
    background( 0);
    //check border of ball with 
    if(  y < radius  ){
       speedY = speedY * -1 ;  //reverse speed on impact
     }
     if(y > height - radius){  //has ball hit the bottom
          speedY = speedY * -1 ;  //reverse speed on impact
          y = height-radius-1; //reset position out of impact zone
     }
     if( x < radius || x > width-radius){ //check for impact with left or right border
       speedX = speedX * -1 ;  //reverse speed on impact
     }
     
     speedY += accelerationY;  
     y += speedY;
     x += speedX;
     
     drawBall(x,y);
};
```