# Transforms

Transformations are functions that can be used to change the physical configuration of the drawing canvas.  This can provide powerful design techniques.  The following transformations can be applied to the canvas: [See Khan Academy Tutorial](https://www.khanacademy.org/computing/computer-programming/programming-games-visualizations/programming-transformations/a/translation).  Based on this [Processing Tutorial](https://www.processing.org/tutorials/transform2d/)

* **translate\( x, y \)**   //move the origin to position\(x,y\),then all shapes are now drawn relative to the new position of the origin.  It is often easier to move the canvas origin, when trying to draw objects that have some geometric relation with each other, such as a joint or point of rotation. 

* **rotate\( angle \)** // rotate the canvas through angle \( degrees / radians \)in the clockwise direction for positive values of angle.  All subsequent shapes are drawn on the rotated canvas, until resetMatrix() or popMatrix() have been called.

* **scale\( x, y \)** //  changes the size of the canvas: larger or smaller - also impacts strokeWeight

### Transformation Matrix

The transformation `matrix` is a global data-table that stores the configuration information of the canvas.  The default values for the matrix can always be reset by calling the function: `resetMatrix()`.  This resets the canvas so the origin is at the upper left corner, and resets rotation to 0 degrees and scaling to 1.0.

### resetMatrix\(\)

The resetMatrix\(\) function sets the origin back to the original, upper-left corner of the canvas, and it removes all other pushMatrix, popMatrix \(snapshot\) data from the transformation-history stack.

### pushMatrix\(\), popMatrix\(\)

The `pushMatrix()` function stores the current state of the transformation Matrix in a **stack** structure, it is like a snapshot is taken of the current transform values and that is saved for later use.  Then the `popMatrix()` function can be used to retrieve the most recent state of the transformation matrix that was stored on the **stack**

##Example - Animated Position and Rotation

Rotate Ellipses 

In the image below, we can look at 2 different approaches for animating ellipses.

1. Animation requires use of the draw loop, and a global variable: ``xPos``, that's incremented within the draw loop: ``xPos++``

2.  Rotation of objects requires that the canvas origin must be moved to the center of the object, then rotate( angle) causes the canvas to rotate - around the object's center.  If ``angle`` is a global variable that's incremented, then rotation will be animated: ``angle++``

The blue ellipse has ``xPos`` animated:
   

```java
 //simplified code snippet
    var xPos=0;

    var draw=function(){
        fill( 0,0,255); // blue
        ellipse( xPos, 100, 30, 60); 
        xPos++;  //increment
    }

```


The yellow ellipse is animated, through translation of the origin, and rotation around the origin, the ellipse is drawn at the origin:  ellipse( 0,0,100, 30);
    

```java
//simplified code snippet
    var xPos=0;
    var angle = 0;

    var draw=function(){
        fill( 255, 255,0);//yellow
        translate(xPos, 200);
        rotate( angle ); //rotate around origin
        ellipse( 0, 0, 100, 60);  //drawn at origin
        xPos++; //increment
        angle++; //increment
    }
```


[Link to example project](https://www.khanacademy.org/computer-programming/transforms-for-animated-rotation/6642382780170240)

![](/assets/Screenshot 2017-09-07 09.02.50.png)


### Relative Positioning Animation - PushMatrix / PopMatrix
Below is an example of how transforms can be used to create a simple character, we can use pushMatrix\(\) and popMatrix\(\) to save and retrieve canvas configuration settings as noted in the image below.  pushMatrix and popMatrix are designed to be used together, you call pushMatrix when you know that you will want to return to the current configuration.  This is common when trying to create symmetry relative to a fixed reference point like the character's nose.

![](transforms.png)

[Link to Code Example: Khan Academy Program with Transforms](https://www.khanacademy.org/computer-programming/transformations-pushmatrix-popmatrix/5558061535199232)

