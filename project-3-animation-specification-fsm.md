###Project 3

**Project 3   - Animation Example**

https://www.khanacademy.org/computer-programming/spin-off-of-animationdemo/6167117722943488



Step 1:  Identify States and Events in your Animation

The tables below show the possible values for the **state:** `waveState` in the linked Khan Academy Project

![](/assets/Screenshot 2017-10-18 12.39.54.png)

![](/assets/Screenshot 2017-10-18 12.40.02.png)

###FSM State Transition Table
Below, the FSM State Transition Table shows a full listing of allowable transitions between system states that can happen when the corresponding event occurs.  We can see that if the system is in the state where `waveState` equals `UP`, then, if the event occurs: `armAngle >= maxAngle` , then the system will transition such that the state will now be: `waveState` equals `DOWN`.



![](/assets/Screenshot 2017-10-18 12.40.13.png)

###FSM State-Transition Diagram
The image below is a stylized version of an FSM State-transition diagram, normally each state is represented by a circle, as with the Start state.

