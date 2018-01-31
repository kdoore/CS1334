# Transforms

Transformations are functions that can be used to change the physical configuration of the drawing canvas.  This can provide powerful design techniques.  The following transformations can be applied to the canvas: [See Khan Academy Tutorial](https://www.khanacademy.org/computing/computer-programming/programming-games-visualizations/programming-transformations/a/translation).  Based on this [Processing Tutorial](https://www.processing.org/tutorials/transform2d/)

* **translate\( x, y \)**   //move the origin to position\(x,y\),then all shapes are now drawn relative to the new position of the origin.  It is often easier to move the canvas origin, when trying to draw objects that have some geometric relation with each other, such as a joint or point of rotation. 

* **rotate\( angle \)** // rotate the canvas through angle \( degrees / radians \)in the clockwise direction for positive values of angle.  All subsequent shapes are drawn on the rotated canvas, until resetMatrix() or popMatrix() have been called.

* **scale\( x, y \)** //  changes the size of the canvas: larger or smaller - also impacts strokeWeight

### Transformation Matrix

The transformation `matrix` is a global data-table that stores the configuration information of the canvas.  The default values for the matrix can always be reset by calling the function: `resetMatrix()`.  This resets the canvas so the origin is at the upper left corner, and resets rotation to 0 degrees and scaling to 1.0.

### resetMatrix\(\)

The resetMatrix\(\) function sets the origin back to the original, upper-left corner of the canvas, and it removes all other pushMatrix, popMatrix \(snapshot\) data from the transformation-history stack.


```java

var draw = function(){
   
    translate( 100, 100);
    rotate( 30 );
    rect( 0, 0, 50, 50); //rotated rect drawn at 100,100
    resetMatrix();
    //rectangle below is not impacted by prior transforms
    //since resetMatrix reset to transforms to default 
    rect( 0, 0, 50, 50); //rect drawn at canvas origin: 0,0

}

```

### pushMatrix\(\), popMatrix\(\)

The `pushMatrix()` function stores the current state of the transformation Matrix in a **stack** structure, it is like a snapshot is taken of the current transform values and that is saved for later use.  Then the `popMatrix()` function can be used to retrieve the most recent state of the transformation matrix that was stored on the **stack**
pushMatrix and popMatrix must be used in pairs, pushMatrix is used to save the state of the transforms that have already been applied prior to pushMatrix( ) being called.  Once popMatrix() is called, all changes to transforms that happened after the most recent pushMatrix( ) are undone, but all prior transforms still impact shapes drawn after pushMatrix( ).  To summarize, any transforms set within a pair of pushMatrix( ) and popMatrix( )  functions do not impact any code outside of that pair of functions.  However, any transforms applied prior to pushMatrix( ) remain.  This allows for creating relationships between shapes such as a character's center point, and rotation that would occur at a character's shoulder, elbow, and wrist.

```java

var draw = function(){
   
    translate( 100, 0); //shift origin horizontal 
    pushMatrix();
      translate( 0, 100); //shift origin vertically
      rotate( 30 ); 
      rect( 0, 0, 50, 50); //rotated rect drawn at 100,100
    popMatrix(); //undoes transforms since last pushMatrix( )
    //rectangle below is impacted by original translate(100,0), but none of the changes inside pushMatrix(), popMatrix( ) pair.
   
    rect( 0, 0, 50, 50); //rect drawn at: 100,0
}

```

