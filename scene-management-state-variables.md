###Scene Management - State Variables

In the Khan Academy code examples, they provide an example of how to design logic for showing game-type scenes.  The logic is the same as the Finite State Machine logic that we've used for our character.  

###Finite State Machine for Scene Management
Finite State Machine structure can be used to design a system if we have a finite number of states, such that we can list them in a table or diagram.  In addition, we have a finite set of events that can cause the system to change state.  Finally, an FSM must have a memory-variable that keeps track of the current state of the system.


Example Project: 
https://www.khanacademy.org/computer-programming/scene-management-nov6/5124079971139584

###FSM:  States, storyState  
We can use an FSM structure if we have a finite set of possible states for the system.  For this example, we have 3 scenes, so we can say we have 3 states.  In addition, we need a variable to keep track of the active State, here we'll use `var currentState` and we need to initialize it to a valid and meaningful value.  

   var currentState = 1; // can have values 1, 2, 3 
   
  ###Events:  
  We need to define events that can change the state of the system.  We can use the keypress event, we can say that the RIGHT arrow key is an event that will change to the next scene.  We can also say that the LEFT arrow key can change the scene back to the previous scene.  
  
  ###FSM Diagram 
  The diagram below shows an example for scene management state-event logic where 3 events and 3 states are defined.  The FSM diagram captures the logic to control scene management, however, this is defined at an abstract level which is independent of any specific programming language.  The events listed: Start, Right, Left, are concept that could be implemented in a number of ways such as using keypress events or custom buttons, so the FSM specification _**gives a conceptual model of the event-driven system**_, where this system could be implemented using a wide variety of technology.
  
  ![](/assets/Screen Shot 2017-11-27 at 11.45.05 AM.png)


###Example Program
In the program below, we define currentState to keep track of the current state, We define KeyPress events that listen for LEFT and RIGHT arrow keys to be pressed, if these buttons are pressed,  the nextScene( ) or prevScene() functions are called to determine which is the next scene to be set as the currentState and which scene to draw;


```java
  
var currentState = 1; ///other valid values are 2, 3
var moonAngle = 220;  

var drawScene1 = function(){
    fill(255, 0, 0);
    rect( 0,0, width, height);
    fill(20, 19, 19);
    text("Scene 1", 200,200);
};

var drawScene2 = function(angle){
    fill(30, 0, 255);
    rect( 0,0, width, height);
    pushMatrix();
    translate(width/2, height);
    rotate( angle);
    fill(255, 247, 247);
    ellipse( 300, 0,50,50);
    popMatrix();
    fill(20, 19, 19);
    text("Scene 2", 200,200);
};

var drawScene3 = function(){
    fill(3, 245, 39);
    rect( 0,0, width, height);
    fill(20, 19, 19);
    text("Scene 3", 200,200);
};


///logic to manage scene changes
var nextScene = function(){
    if( currentState === 1){
        currentState = 2; //change state
        moonAngle =220;
        drawScene2();
    }
    else if( currentState === 2){
        currentState = 3;
        drawScene3();
    }
    
};

var prevScene = function(){
    if( currentState === 2){
        currentState =1;
        drawScene1();
    }
    else if (currentState ===3){
        currentState =2;
        moonAngle =220;
        drawScene2();
    }
};

///Start the program
drawScene1();

var draw= function() {
    if(currentState === 2 ){
     drawScene2(moonAngle  );
     moonAngle+= 0.25;
    }
};

var keyPressed = function(){
    if( key.code === CODED){
        if( keyCode === RIGHT){
            nextScene(); 
        }else if(keyCode === LEFT){
            prevScene();
        }
        
    }
};
  

```


