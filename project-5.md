#Project 5 - Scene Management

For project 5, you will be integrating scenes into your previous project.  We'll use a Finite State Machine to model the logic to manage changing scenes.  

###Nested Finite State Machines 
For our final project, we'll have 2 different Finite State Machines, since we had already implemented a FSM to control our character's animation.  So, the diagram below shows that there are nested FSM's in our project.  The FSM's are independent, each relies on it's own state variable to keep track of the current state.  We need to provide code to implement the conceptual model captured in each FSM's structure.

![](/assets/Screen Shot 2017-11-27 at 12.45.24 PM.png)


###Resources and Example Projects
You will follow the instructions for creating scenes in the Khan academy tutorials for: SceneManagement.
https://www.khanacademy.org/computing/computer-programming/programming-games-visualizations#programming-scenes
 
See example project - Khan Academy:  https://www.khanacademy.org/computer-programming/project-5-example-v2/5126765991624704

[Gitbook - Scene Management](/scene-management-state-variables.md)

###Buttons using Object Literal Syntax
In the example project, I have used object literal syntax to specify properties for 2 button objects.  This provides a nice way to organize, access, and modify data associated with a single object.

Here is code to define 2 object literals, and example code to show how to use these objects in custom functions.

Inside mouseClicked( ), we call functions that we've designed to take a button object as input parameter. Within the custom functions: drawButton, restartClicked, and checkClicked, the button's properties are accessed using dot notation.  For both button objects, we've defined the same properties, we can easily add additional buttons to the project using the same format.   
    

```java
 
//use global object-literal for buttons
//defines property and value pairs to be associated
//with a single object-type variable
    
var nextButton = {
    x: 316,  //property x has value 316
    y: 14,
    w: 68,
    h: 28,
    label: "Next >>",
    buttonOn: false
};

var animationButton = {
    x: 15,
    y: 349,
    w: 116,
    h: 29,
    label: "Restart Animation",
    buttonOn: false
};
    
//Function takes a btn object as an input parameter
//inside the function use dot notation to access object properties
var drawButton=function( btn){
    fill(12, 201, 192);
    rect( btn.x, btn.y, btn.w, btn.h);
    fill(54, 54, 54);  //text fill is white
    text( btn.label, btn.x +10, btn.y + (btn.h/2) + 5);
}; 

//called from mouseClicked( )
//to see if animation button was clicked
var restartClicked = function( btn){
     if( mouseX > btn.x && mouseX < btn.x + btn.w && mouseY > btn.y && mouseY < btn.y + btn.h){
        initializeScene2();
        btn.buttonOn = false; ///turn off button
    }
};

//called from mouseClicked()
//to check if nextButton is clicked
var checkClicked = function( btn){
     if( mouseX > btn.x && mouseX < btn.x + btn.w && mouseY > btn.y && mouseY < btn.y + btn.h){
        nextScene();
        btn.buttonOn = false; //turn off button
    }
};

//Processing mouseClicked event handler
var mouseClicked=function(){
   checkClicked( nextButton);
   restartClicked( animationButton);
};
      
```

###Restart Animation:  InitializeScene2( ) Function
To restart the animation within Scene2, we've created a button:  animationButton that is drawn inside the draw function if the currentState is Scene2. 



```java
 
var draw= function() {
    if(currentState === 2 ){
        drawScene2( moonAngle  );
        moonAngle+= 0.15;  //moon animation
        moonShadow +=0.05;  //shadow animation
     
        ////ADD DRAW LOOP CODE FROM PROJECT 4 
        checkCount();
        angle = checkArmState(angle);
        drawCharacter(x,y,angle); 
        ///end of Project 4 code
   
        ///Draw Animation Reset Button
        drawButton( animationButton);
    } /


```

