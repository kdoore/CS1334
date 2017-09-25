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

###Draw A Plant - Start with lines for a stem.

For code to draw a stem, we can use a line, we will want to reposition flowers, so the 2 line points must be function input parameters.  

The function below draws 3 lines, with the middle line to hold the flower.


```java

var drawFlower = function( baseX, baseY, stemX, stemY, stemAngle){
    
    //start by drawing lines from the base to the stem points
    
    stroke(41, 133, 57);  //green
    strokeWeight(10);
    line(baseX,baseY, stemX-18, stemY+40);
    line(baseX,baseY, stemX+18, stemY+10);
    line(baseX,baseY, stemX, stemY);
    
    ///move the origin to the stemX, stemY point
    pushMatrix();
    translate( stemX, stemY);
    rotate(stemAngle); //placeholder - we might want to be able to rotate the flower before drawing it
    
    drawFlower( ); //placeHolder until we get this code written
    //fill(255,0,0); //red to mark origin
    //ellipse(0,0,10,10); //mark the origin so we can see it
    popMatrix();
    
}
```
###Draw a Flower - start with more stem lines
We can begin by drawing more stem lines - from the stem connection point to the flower's center point, then we'll translate the origin to the flower's center point.

```java

var drawFlower = function( stemX, stemY, centerX, centerY, flowerAngle){
    //start by drawing a line from stemX,stemY to centerX, centerY
 
    stroke(41, 133, 57);
    strokeWeight(10);
    line(stemX,stemY,centerX,centerY); //draw stem section
    
    //move origin to flower center
    pushMatrix();
    translate( centerX, centerY);
    rotate( flowerAngle);//place holder in case we want to rotate the flower
    
    ///drawing petals code goes here - placeholders
    drawPetal( );
    drawPetal( );
    drawPetal( );
        
    //fill(255,0,0); //red to mark origin
    //ellipse(0,0,10,10); //mark the origin so we can see it
    popMatrix();
    
}

```

###Draw Petal Logic

[Draw Petal Logic ](https://www.khanacademy.org/computer-programming/petallogic/6664207964766208)



```java

//draw 1 petal
var drawPetal = function( centerX, centerY, petalAngle, scaleX, scaleY){
pushMatrix();
    translate(centerX, centerY);
    scale(scaleX, scaleY);
    rotate(petalAngle);
    beginShape();
    vertex(4,4);
    bezierVertex(55,45,30,57,6,37);
    bezierVertex(50,154,107,53,4,4);
    endShape();
popMatrix();
};


var petalAngle = 178;
fill(123, 60, 217);
drawPetal( 200,200, petalAngle, 1.3,1.3);
drawPetal( 200,200, petalAngle, -1.3,1.3);
```

