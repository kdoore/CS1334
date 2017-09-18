#Functions
Functions allow us to create modular sections of code to add structure and organization to our code.  We can name these chunks of code, which makes it easy to **call** the functions so they can execute in the desired order.  We have been using, or *calling* functions that are part of the Processing Library.  But now we'll learn how to write our own custom functions.  Therefore we need to understand function syntax for javascript.

###Function Definition
The following are terminology for the specification of a function:

1. Function Name
2. Function Input Parameters - how we send values into a function
3. Function Body - code statements within the function to do function task
4. Function Return Value - how we can get a value out of a function

###Function Definition Code:

```javascript

var myFunctionName = function ( param1, param2){
  // function body has code statements in the function body
    rect(param1, param2, 50,50);  //use input parameters
    var someReturnValue = 1;  //local variable to function

    return someReturnValue;
}

// execute the function - make sure to match the function signature
myFunctionName( 10,20); 

//execute the function and store the returned value
var retVal = myFunctionName( 30,30);
println( "Returned value " + retVal);  //retVal = 1

```
###Function Signature:
The function signature refers to the function Name and Input Parameters, it's the first line of a function definition. The function Signature specifies the format that should be used when calling the function:
 
  FunctionName ( param1, param2 )  // function signature
  
###Calling a Function
When we want to execute a function, we must provide values to match each input parameter defined in the function.  The values are used to initialize each function parameter value, which are used as local variables in the functions.  




###Function Overloading
Function Overloading refers to when 2 or more functions are defined that use the same function name, but use a different number of function input parameters.  Function overloading provides convenience to users of your functions, because it recognizes that sometimes it is nice to be able to specify more details that can be used in the function execution.  Each Function that is overloaded has it's own function definition.  We have used overloaded functions when we've used the fill() function:  fill(r,g,b), fill(r,g,b,a), fill(grayscale);    