# KeyPress Logic

The example project below shows several ways to use processing's key press events and boolean variables to add keyboard interaction to a program.

Example Khan Academy Project: [https://www.khanacademy.org/computer-programming/keypressed-and-key-keycode/6732372287094784](https://www.khanacademy.org/computer-programming/keypressed-and-key-keycode/6732372287094784)

## Using Special Keys:  UP and DOWN Arrows

The example project below uses UP and DOWN arrows to change the value of variable: targetY, this is a global variable that's use to animate a rectangle by passing this value into the drawTarget function where it's used to control the y position of the rectangle.

Example: [https://www.khanacademy.org/computer-programming/moving-target/5411884593774592](https://www.khanacademy.org/computer-programming/moving-target/5411884593774592)

```java
var targetY = 100;
var drawTarget = function( tX, tY, tW, tH){
fill(0, 153, 255); //blue
rect( tX, tY, tW, tH);
};

var draw = function(){
    background(0);
    if(keyIsPressed){ 
        if( key.code === CODED){ 
            if(keyCode === UP){ 
            targetY--; } 
            else if(keyCode === DOWN){ 
        targetY++; 
        } 
    } 
}
    drawTarget( 300, targetY,30, 100);
};
```

## Processing keyPressed event:

The example code below uses the processing keyPressed event function. The code within the function is only executed when a key has been pressed, it's only executed once per key-press event. The example code below has logic that displays keys or sentences on the canvas based on the key that was pressed.

```java
    var keyPressed = function( ){
        fill(0);
        text( key, mouseX,mouseY); //display current key

    // Conditionally display based on string value
    if (key.toString() === '!') {  //type ! key
        text("I'm excited too!!", 100, 150); 
        }
    if( key.code === 42) {  //type *  key
        text("You’re a star", 100, 150);  
        }
    //check for special keys 
    if( key.code === CODED){  //special keys
        if(keyCode === UP){
            text("UP", 100, 300);      
        }    
        text ("special key", 200,200);
    } // end if

};     // end keyPressed function
```

