#Buttons

We can create custom buttons to let the user interact with our program.  In order to do this, we need: 
    - a visual indicator for the button
    - code to detect if the mouse has been clicked inside the button
    - a variable that keeps track of the button's state: on or off 

For each button, we'll need to have logic in the mouseClicked event function to check if the mouse is within the button's bounding box.  


###Example code: 
Simple Button: [https://www.khanacademy.org/computer-programming/simple-button/5482448616357888](https://www.khanacademy.org/computer-programming/simple-button/5482448616357888)

In the code below, we have a function to draw a button, where the color of the button changes depending on the global state variable: buttonOn.  This state variable has it's value changed in the mouseClicked function if the button was clicked.  The button starts in the 'off' state, where buttonOn is set to false.  Each time the mouse is clicked while it's within the button's boundary, the value of buttonOn is reversed, if it was true, then it's set to false.  This creates a toggle button that changes between being on and off.  Within the drawButton function, the fill color for the button is determined based on the state of this buttonOn variable.  For this course, we'll treat state variables as global objects since we need to check the value within the mouseClicked() or mousePressed function.


```java
var x = 100;
var y = 100;
var w = 100;
var h = 50;
var buttonOn = false;  //variable to track the button's state

var drawButton = function(x,y,w,h){
    fill(240, 5, 60); //red is off
    var btnText = "OFF";
    if( buttonOn === true){
        fill(14, 201, 98); //green
        btnText = "ON";
    }
    rect(x,y,w,h); //draw button rectangle
    fill(252, 252, 252);  //fill for text
    textAlign(CENTER);
    text(btnText,  x +(w/2) ,y + (h/2)+5);
};

var draw = function() {
    background(255);
    drawButton(x,y,w,h );
};
var mouseClicked = function(){
    if( mouseX > x && mouseX < x+w && mouseY > y && mouseY < y + h){
        buttonOn = !buttonOn;  //toggle button between on and off
    }
};

```

###Javascript Object Literals
Javascript has a convenient way to store a group of data that is all related to 1 object, object literal notation. For using Javascript object literals, you will a global variable with a code block that contains property name: attribute value pairs, these are separated by commas. Object literals allow us to treat the data associated with an object as one bundle of information. 

In the code below we can see that we've created an object literal with the name: btn1

Example Code: [https://www.khanacademy.org/computer-programming/button-with-object-literal-data/4584211168559104](https://www.khanacademy.org/computer-programming/button-with-object-literal-data/4584211168559104)

this object can access any of it's property: value pairs

```java

var btn1 = {
    x: 100,
    y: 100,
    w: 150,
    h: 50
};
  
 //function that takes an object literal      
var drawButton= function( btn ){
     fill( 255,0,0);
     rect( btn.x, btn.y, btn.w, btn.h);
   } 

drawButton( btn1 );    //call the function
```

Example Project using Javascript Object Literals for Data

https://www.khanacademy.org/computer-programming/simple-button2/6732500190035968

 

JSON is a similar object syntax used as an open data standard for the web.  [](https://en.wikipedia.org/wiki/JSON)

Example Project using Javascript Object Literals for Data

https://www.khanacademy.org/computer-programming/simple-button2/6732500190035968



Khan Academy Tutorial: [Khan Academy Link](https://www.khanacademy.org/computing/computer-programming/programming-games-visualizations/programming-buttons/a/a-button-function)



