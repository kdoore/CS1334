#Collision between Objects

When we want to animate objects colliding, we need to consider the geometry of each object, and determine when the object geometry overlaps.  For this example, we'll look at collision between an ellipse and a rectangle.

Example Khan Academy Project:

[https://www.khanacademy.org/computer-programming/colliding-objects/5192472599134208](https://www.khanacademy.org/computer-programming/colliding-objects/5192472599134208)

The image below shows the geometry for the 2 objects used in this example.  We have a ball object and a target object.  The ball object is defined by the following: 

    center:  bX, bY
    radius: bR  
    diameter: 2 * bR

The target is a rectangle defined by the following:

    upper-left point: tX, tY
    width: tW
    height: tH

As seen in the image below, the geometries overlap on the left edge of the rectangle when the following is true: 
    bX + bR > tX  //the right edge of the ball is larger than the left edge of the target
    
![](/assets/Screenshot 2017-11-15 12.59.48.png)

