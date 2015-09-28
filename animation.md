#Animation:  Draw Loop
In order to create animations,  Processing repeatedly executes a special function: `draw()`.  Each time the draw() function is executed (60 times /per second), every line of code in the draw function is executed to determine what graphical marks should be rendered on the screen.  So, in order for us to create animations, we must write the definition of the draw() function, then, during our program's execution, Processing checks our code to see if we have correctly defined a ``draw()`` function, then it executes the code within the ``draw()`` function 60 times per second.  

###Processing Calls the draw() Function
With other processing functions that we've used before, like ``rect(x, y, w, h)`` or ``fill(r, g, b)``, we have written a program statement to *calls* these processing functions.  However, with the ``draw()`` function, we never actually *call* the ``draw()`` function, instead, Processing calls the ``draw()`` function for us.

###Guidelines for Animation in Processing
1.  The draw() function can only be defined 1 time in a program.  
2.  Create a global variable that is used to set the value of some visible property of a graphical element: position, size, rotation, color, etc.
3.  Modify the value of the variable each time the draw() function executes
4.  Do not have a local variable of the same name as your global animation variable within the draw loop or it will be reset each time draw() is executed, it will also hide the global variable inside the draw() function.
5.  Call resetMatrix() at the end of each draw() function if you have modified any transformation properties since the default resetMatrix() may not be functioning correctly.
6.  Set the background(R, G, B) as the first line of code in the draw() function if you want stop-frame type animation.  
7.  If in colorMode(HSB), you may need to create a white ``fill(255)` rectangle the size of the canvas, since the background function doesn't always show the correct color.