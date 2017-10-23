#Repetition - Loops

When we have some set of logic that needs to be executed multiple times, then we can use a loop control structure to have a chunk of code repeated.  There are 2 main types of loop control structure:
    1. `while` loop - execute repetition as for as long as a test condition remains true
    
    2. `for` loop   - execute repetition for a specific number of times
    
    
    
###While Loop
When we have a set of statements that we want repeated, but only while a certain condition remains true, then the while loop provides a structure that matches this situation. 

In the code below, we use a while loop to determine how many bars to draw. 

Since we're repeatedly drawing the same shape, a rectangle that has it's height set as the height of the canvas, where we are changing the x position, w: the rectangle's width, and hue of each rectangle, we can put that logic in a function and call the function within a while loop.  The loop should stop when the x position of the next bar is larger than the canvas width. Since we are using random width values, we're not sure exactly sure how many bars will be drawn, so the while loop structure works well in this situation.


**Example: **Draw Rainbow Bars of differnt width across the canvas



```java
colorMode(HSB);  //HSB colormode 
background( 0);
var x=0;
noStroke();

var drawColorBars = function( x,w ){
    var hueVal= map(x, 0,width, 0,255) ;
    fill(hueVal, 255, 255);
    rect(x, 0, w, height);
    };
    
var drawBars = function(){
while (x <= width){
    var w = random(1,12);
    x += w;
    drawColorBars( x, w);
  }
};


```

![](/assets/Screenshot 2017-10-23 12.41.29.png)