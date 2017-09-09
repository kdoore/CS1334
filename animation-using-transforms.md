#Animation using Transforms

### Animate Rotating Ellipses - Use Transforms

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
        resetMatrix();
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

