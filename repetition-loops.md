#Repetition - Loops

When we have some set of logic that needs to be executed multiple times, then we can use a loop control structure to have a chunk of code repeated.  There are 2 main types of loop control structure:
    1. `while` loop - execute repetition as for as long as a test condition remains true
    
    2. `for` loop   - execute repetition a specific number of times
    
    
    
###While Loop
When we have a set of statements that we want repeated _while_ a certain condition remains true, then the while loop provides a structure that matches this situation. 

In the code below, we use a while-loop to repeat drawing rectangles of different width, x position, and hue across the canvas. 

In this example, we are repeatedly drawing the same shape, a rectangle, where it's height set as the height of the canvas. Each time we draw a new rectangle, we need to change the following values:  w: the rectangle's width, the x position, and hue of each rectangle.  We can put the logic into a function, where we pass in values of w, x, hue each time, and call the function within a while-loop.  The looping should stop when the x position of the next bar is larger than the canvas width. Since we are using random width values, we're not sure exactly sure how many bars will be drawn, so the while loop structure works well in this situation.  The number of bars drawn each time we run the program is slightly different due to the random width for each bar.  


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

