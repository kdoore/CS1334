###Finite State Machine

Finite State Machine (FSM) is abstraction to simplify reasoning about dynamic, event driven systems.

To represent a system using a finite state machine, it is necessary to identify all possible states for the system, and to identify all possible events that can change the state of the system.

Once a system has been defined using FSM notation, it becomes easier to design the program logic for implementing the animation.

FSM's are commenly used to control animation logic.  The Unity plugin, Playmaker, uses finite state machine logical structure to create visual scripting interface.   Unity has Mechanim which is a visual scripting environment for creating animations, it uses finite state machine logic for controlling which animation clip is played, and the logic for switching between animation states, where each animation state corresponds to an animation clip. FSM's work well for game scripting because games can be understood as a series of events, that change the state of the system.  An event causes a state-change and that can trigger an action to occur.

Project 3   - Animation Example

https://www.khanacademy.org/computer-programming/spin-off-of-animationdemo/6167117722943488

Step 1:  Identify States and Events in your Animation