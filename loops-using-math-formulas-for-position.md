###Loops with Mathematical Formulas for Position

Often we need to repeat execution for some some block of code.  There are 2 basic control structures that can be used for repeating blocks of code, these are both considered as _**loop**_ control structures because we can think of repetition as a looping procedure.  

###For-loops  - Count Controlled Loops
When we have code we want repeated, often we know exactly how many times we need the repeated code to be executed.  A for-loop has a loop-control structure that provides the code-structure needed to control how many times the loop code is executed.

`for( var i = 0; i< 100; i++ ) // loop control structure`

1. Declare and initialize a variable to control the number of times a loop is executed:  `var i = 0; `  //this variable is the loop-control variable, it's used to control how many times the loop code is executed.

2.  Test to see if loop code should be executed:  ` i < 100;'  //this is the test condition, we do a comparison to see if the count variable has exceeded the maximum  number of times to execute the loop.  

3.  Modify the loop-control variable:  ` i++`   //here we are modifying the value of the loop-control variable each time the loop is executed, this must modify the loop variable to insure that at some point it fails the conditional test from step 2, we must insure that the loop stops or we'll have infinite looping and that will crash our program.


Often we'll use the loop control variable to help calculate the changed positioning for each new item drawn.  


###Khan Academy Example of for-loops
The Khan Academy's documentation provides 2 examples of using the loop control variable to control positioning of elements:

https://www.khanacademy.org/computer-programming/for-var-i-0-i-8-i-1/877960284

```
// draw 8 evenly-spaced circles
for (var i = 0; i < 8; i+=1) {
    var x = i * 50;
    ellipse(x + 20, 200, 10, 10);
}

// draw 100 evenly-spaced points
for (var j = 0; j < 100; j += 1) {
    var x = j * 4;
    point(x, 300);
}

```

###Example Project 
In the example image below, over 1000 ellipses are drawn on the canvas using a for-loop.  When using loops to draw elements on the screen, we need to have some formula to change the value of x, y for each element that's drawn, otherwise they'll all be drawn on top of each other and there would be no point in using the loop.


https://www.khanacademy.org/computer-programming/loopy-patterns/6155489581400064

![](/assets/Screenshot 2017-10-19 09.32.08.png)

```

//this function draws a pattern using mathematical formula 
//to determine x,y position of each ellipse
//Use a for-loop to repeat drawing each ellipse - draw 100 ellipses using the loop
//a is random point generated in width range minX to maxX
//b is a random point generated in height range: minY to maxY
var drawPattern= function( xPos, yPos){
translate( xPos,yPos);
  for( var i=0; i< 1000; i++){
    var a = random( -100,100);  //a is width min,max for pattern
    var b= random( -100, 100); //b is height min, max for pattern
    //use crown pattern - all ellipses are drawn within a region defined by the following math equations
    var  x = a*cos(b/2);  //x position for each flower
    var y = -abs(a*sin(b+90))  ; //y position for each flower
    fill(128, 255, 0);
    ellipse( x,y,5,5);  //use calculated x,y values for each ellipse positioning
    }// end for loop
    };
    
 
 //use another for-loop to call the drawPattern function 20 times with different values for x and y so that you draw the pattern 20 times  
background(50);
var x= 200;
var y = 200;
drawPattern( x,y); 
```

