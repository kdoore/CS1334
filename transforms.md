# Transforms

Transformations are functions that can be used to change the physical configuration of the drawing canvas.  This can provide powerful design techniques.  The following transformations can be applied to the canvas: [See Tutorial](https://www.khanacademy.org/computing/computer-programming/programming-games-visualizations/programming-transformations/a/translation).  Based on this [Processing Tutorial](https://www.processing.org/tutorials/transform2d/)

* **translate\( x, y \)**   //move the origin to position\(x,y\)

* **rotate\( angle \)** // rotate the canvas through angle \( degrees / radians \)

* **scale\( x, y \)** //  changes the size of the canvas: larger or smaller - also impacts strokeWeight

### Transformation Matrix

The transformation `matrix` is a global data-table that stores the configuration information of the canvas.  The default values for the matrix can always be reset by calling the function: `resetMatrix()`.  This resets the canvas so the origin is at the upper left corner, and insures that there's no rotation or scaling.

**translate\( x, y \) ** moves the _origin_ to the point: \( x, y \), then all shapes are now drawn relative to the new position of the origin.  It is often easier to move the canvas origin, when trying to draw objects that have some geometric relation with each other, such as a joint or point of rotation.  

**rotate\( angle \) **rotates the _canvas_ in the clockwise direction for positive values of angle.  All subsequent shapes are drawn on the rotated canvas, until resetMatrix() or popMatrix() have been called.

  
**Example: ** Draw 4 circles to represent a partial-compass with the following directions: N, NE, E, SE, S indicated by a circle and text:


![](/assets/Screenshot 2017-07-28 19.07.31.png)

_**Problem 1.** _ How to Draw objects, in reference in the center of the canvas. 
**_Solution 1._**  calculate position values for all objects, relative to the standard origin. Given we are trying to create a compass, this seems unintuitive, it doesn't consider the rotational symmetry of the compass, which should allow for a simpler approach. 

Sample code for ellipse positions: 








### resetMatrix\(\)

The resetMatrix\(\) function sets the origin back to the original, upper-left corner of the canvas, and it removes all other pushMatrix, popMatrix \(snapshot\) data from the transformation-history stack.

### pushMatrix\(\), popMatrix\(\)

The `pushMatrix()` function stores the current state of the transformation Matrix in a **stack** structure, it is like a snapshot is taken of the current transform values and that is saved for later use.  Then the `popMatrix()` function can be used to retrieve the most recent state of the transformation matrix that was stored on the **stack**

Below is a simple example of how transforms can be used to create a simple character, we can use pushMatrix\(\) and popMatrix\(\) to save and retrieve canvas configuration settings as noted in the image below.  pushMatrix and popMatrix are designed to be used together, you call pushMatrix when you know that you will want to return to the current configuration.  This is common when trying to create symmetry relative to a fixed reference point like the character's nose.

![](transforms.png)

[Link to Code Example: Khan Academy Program with Transforms](https://www.khanacademy.org/computer-programming/transformations-pushmatrix-popmatrix/5558061535199232)

