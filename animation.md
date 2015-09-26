#Animation:  Draw Loop
In order to create animations,  Processing repeatedly executes a special function `draw()`.  Each time the draw() function is executed (60 times /per second), every line of code in the draw function is executed to determine what graphical marks should be rendered on the screen.  So, to create animations, we must write the definition of the draw() function, then, during our program's execution, Processing checks our code to see if we have correctly defined a ``draw()`` function, then it executes the code within the ``draw()`` function 60 times per second.  

###Processing Calls the draw() Function
Unlike other processing functions that we've used before, like rect(x, y, w, h) or fill(r, g, b), where we write a program statement which *calls* these processing functions so they are executed in our program.  However, with the ``draw()`` function, we never actually *call* the ``draw()`` function, instead, Processing calls the ``draw()`` function for us.

