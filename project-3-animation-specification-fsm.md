###Project 3

**Project 3   - Animation Example**

https://www.khanacademy.org/computer-programming/spin-off-of-animationdemo/6167117722943488

Simplified Animation Examples

https://www.khanacademy.org/computer-programming/animation-demo-simple/5581835098324992

https://www.khanacademy.org/computer-programming/simple-rotateanimation/6227637252587520

Step 1:  Identify States and Events in your Animation

The tables below show the possible values for the **state:** `waveState` in the linked Khan Academy Project

![](/assets/Screenshot 2017-10-18 12.39.54.png)

In this animation project, the states are represented by a variable: `waveState`, and at any point in time, the system is in one of three possible states: `UP`, `DOWN`, `STOP`.
When the animation is in the `UP` state, the character's arm is moving up, this happens because the variable: `armAngle` is being modified, it's having a positive speed value added to it each frame.  When armAngle reaches the maximum allowable value for this animation, we consider that an event:  the event is that the geometry of the armAngle has reached it's maximum value.  We'll write logic so that each frame we check the value of the arm angle and when the armAngle >= maxAngle, we have to write logic to implement the state change according to the diagram and the table:  waveState transitions from `UP` to `DOWN`.  



```java
//Inside checkArmState function
if(waveState === "UP" && (angle <= maxAngle)){
     if(angle >= maxAngle){   //test for the event
          waveState ="DOWN";   //handle the event - change state
     } //end if
     angle += speed;  //if in UP state, increase angle each frame
}  //end if


```


![](/assets/Screenshot 2017-10-18 12.40.02.png)

###FSM State Transition Table
Below, the FSM State Transition Table shows a full listing of allowable transitions between system states that can happen when the corresponding event occurs.  We can see that if the system is in the state where `waveState` equals `UP`, then, if the event occurs: `armAngle >= maxAngle` , then the system will transition such that the state will now be: `waveState` equals `DOWN`.


![](/assets/Screenshot 2017-10-18 12.40.13.png)

###FSM State-Transition Diagram
The image below is a stylized version of an FSM State-transition diagram, normally each state is represented by a circle, as with the Start state. We can see from the diagram that the system begins in the start state, then, when the reset button is pressed, the system transtions into the `waveState: UP` state.  

![](/assets/Screenshot 2017-10-18 13.05.01.png)

The diagram and tables give us a framework to create simple logic to control our animation.  FSM's provide a powerful way to think about a complex system, once we have a clear specification of the system's states and events, then it is much easier to write code to implement the logic.

If we want to modify our system to add new animations, the first step would be to add new states and events to our tables and diagrams.  We can create an FSM for each animated object in our scene. 