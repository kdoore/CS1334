#Functions to draw Flowers

If we want to use processing functions to draw complex objects like flowers, we'll want to get more comfortable using the processing transform functions: pushMatrix(), popMatrix(), translate( ), scale( ), and rotate( ).

![](/assets/Screenshot 2017-09-25 13.29.24.png)
[Final Code Link](https://www.khanacademy.org/computer-programming/plants_curvevertex/5726921278291968)

Processing has functions to draw complex shapes:  
 
Here's a link to a tool that will allow designing such shapes within the khan academy:

[BezierVertex Tool](https://www.khanacademy.org/computer-programming/beziervertex-drawing-tool/1248677350)

```
beginShape();
vertex(4,4);
bezierVertex(55,43,30,57,6,37);
bezierVertex(50,154,107,53,4,4);
endShape();
```

![](/assets/Screenshot 2017-09-25 13.21.52.png)

If we use the end points and control points to drag our shape to the origin, it'll be easier to use for creating our flower.

###Thinking about drawing a flower

If we were to draw a flowering plant on paper, would we start with plant base or the flower petals?  There's no correct approach, either way can work.

This is also true with programming, but we'll want to create a flexible program so we can draw all shapes and locations of the flower on the canvas.

###
