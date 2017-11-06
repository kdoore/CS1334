###Finite State Machine

Finite State Machine (FSM) is a mathematical abstraction to simplify reasoning about dynamic, event driven systems.

To represent a system using a finite state machine, it is necessary to identify:

        1.  All possible states for the system
        2.  All possible events that can change the state of the system
        3.  For every state, we need to specify what events can occur that cause the system to change to a different state. 
        4.  We need a defined variable that can keep track of the current state that the system is in. 
    

In an FSM system, the system is limited to being in a single state at any time.  This is an important concept, because it allows for simplified logic to be used to describe the dynamic system.  

The system is always in only one of the allowable states. For each state, there is a well defined set of events that that can cause transition from the current state to the next state.  The FSM must have 1 variable to keep track of the current state, the FSM does not maintain any history or memory of the sequence of previous states it has been in.  

Once a system has been defined using FSM notation, it becomes easier to design the program logic for implementing the animation.  Code logic is structured into conditional blocks, organized according to possible system states.  Code is written to define each possible state, and within that state code block, logic must be included to define what action should happen when a valid transition event occurs.

FSM's are commonly used to control animation logic.  The Unity plugin, Playmaker, uses finite state machine logic structure to create visual scripting interface.   Unity has Mechanim which is a visual scripting environment for creating animations, it uses finite state machine logic for controlling which animation clip is played, and the logic for switching between animation states, where each animation state corresponds to an animation clip. FSM's work well for game scripting because games can be understood as a series of events, that change the state of the system.  An event causes a state-change and that can trigger an action to occur.

Finite State Machine -
Once the set of states and events have been defined for a system, then a diagram or table is created to define allowable state transitions for a given event.  This information can be represented in a table with nodes / circles to represent the system states, and arrows / arcs are used to indicate events that cause the system to transition between states.  

See Project 3 - [Animation Specification for Example of FSM](/project-3-animation-specification-fsm.md)

###State Transition Table / Diagram

![](/assets/Screenshot 2017-10-18 12.39.54.png)

![](/assets/Screenshot 2017-10-18 12.40.02.png)

![](/assets/Screenshot 2017-10-18 12.40.13.png)

![](/assets/Screenshot 2017-10-18 13.05.01.png)