#Variable Scope

Variable Scope refers to the location in code where variables can be used in a program.

**Global Variables**  Variables defined outside any functions are visible and usable throughout the program - in any code below where they have been declared.

**Local Variables: ** If a variable is defined as part of a function definition, then the variable _belongs_ to that function. The variable has `local-scope`. The variable is only visible within that function, when that function is being executed, when the function has completed execution, the `local-variables` no longer exist.

**Local Variables Hide Global Variables within a function**
Within a function's definition, if a local variable has the same name as a global variable, the global variable is hidden by the local variable, this is global variable hiding.  Local variables have higher status than global variables within a function.



