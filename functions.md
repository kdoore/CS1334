#Functions
Functions allow us to create modular sections of code to add structure and organization to our code.  We can name these chunks of code, which makes it easy to **call** the functions so they can execute in the desired order.  We have been using, or *calling* functions that are part of the Processing Library.  But now we'll learn how to write our own custom functions.  Therefore we need to understand function syntax for javascript.

###Function Definition




###Function Overloading
Function Overloading refers to when 2 or more functions are defined that use the same function name, but use a different number of function input parameters.  Function overloading provides convenience to users of your functions, because it recognizes that sometimes it is nice to be able to specify more details that can be used in the function execution.  Each Function that is overloaded has it's own function definition.  We have used overloaded functions when we've used the fill() function:  fill(r,g,b), fill(r,g,b,a), fill(grayscale);    