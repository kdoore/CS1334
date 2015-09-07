#Transforms

Transformations are functions that can be used to change the physical configuration of the drawing canvas.  This can provide powerful design techniques.  The following transformations can be applied to the canvas: [See Tutorial](https://www.khanacademy.org/computing/computer-programming/programming-games-visualizations/programming-transformations/a/translation).  Based on this [Processing Tutorial](https://www.processing.org/tutorials/transform2d/)

  -    Translate( x, y )   //move the origin to position(x,y)
  -    Rotate( angle ) // rotate the canvas through angle ( degrees / radians )
  -    Scale( x, y ) //  changes the size of the canvas: larger or smaller - also impacts strokeWeight
  -    

###Transformation Matrix
The transformation ``matrix`` is a global table that stores the configuration information of the canvas.  The default values for the matrix can always be reset by calling the function: ``resetMatrix()``.  This resets the canvas so the origin is at the upper left corner, and insures that there's no rotation or scaling.

###PushMatrix() / Pop Matrix()
The pushMatrix() function stores the current state of the transformation Matrix in a **stack** structure.  Then the popMatrix() function can be used to retrieve the most recent state of the transformation matrix that was stored on the **stack**