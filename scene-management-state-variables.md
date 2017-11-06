###Scene Management - State Variables

In the Khan Academy code examples, they provide an example of how to design logic for showing game-type scenes.  The logic is the same as the Finite State Machine logic that we've used for our character.  

###Finite State Machine for Scene Management
Finite State Machine structure can be used to design a system if we have a finite number of states, such that we can list them in a table or diagram.  In addition, we have a finite set of events that can cause the system to change state.  Finally, an FSM must have a memory-variable that keeps track of the current state of the system.

Example Project: 
https://www.khanacademy.org/computer-programming/scene-management-nov6/5124079971139584

###FSM:  States, storyState  
We can use an FSM structure if we have a finite set of possible states for the system.  For this example, we have 3 scenes, so we can say we have 3 states.  In addition, we need a variable to keep track of the active State, here we'll use `var storyState` and we need to initialize it to a valid and meaningful value.  

   var storyState = 1; // can have values 1, 2, 3 
   
  ###Events:  
  We need to define events that can change the state of the system.  We can use the keypress event, we can say that the RIGHT arrow key is an event that will change to the next scene.  We can also say that the LEFT arrow key can change the scene back to the previous scene.  
  
  

