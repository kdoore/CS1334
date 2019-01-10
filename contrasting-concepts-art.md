#Contrasting Concepts - Contemplative Art
The image below shows an abstract art composition designed to represent the dualism of emotional states:  Relax / Stress.

The idea is to select 2 contrasting concepts and find a way to represent that concept using abstract shapes and colors.

![](/assets/Screen Shot 2019-01-10 at 3.03.52 PM.png)

![](/assets/Screen Shot 2019-01-10 at 3.05.00 PM.png)

[Link to Khan Academy code for this artwork](https://www.khanacademy.org/computer-programming/contrastdesign-mousex/4687668123697152)


```java

rectMode(CENTER); //draw rectangles where x,y is  center point

stroke(107, 105, 105,100); //stroke with transparancy
var rectSize = 50; //initial rectangle size
var sizeMax = 100; //max size of a shape
var sizeMin = 20; //min size of a shape
var radius = rectSize/2; //radius
var c1 = color(0, 255, 187,100); //green w/transparancy
var c2 = color(255, 122, 5,100); //orange w/transparancy

background(255, 255, 255); //set white background one time
    
    
var draw= function() {
   var fraction = map( mouseX, 0, width, 0.0, 1.0);
   var curColor = lerpColor( c1, c2, fraction); //determine color 
   fill(curColor); //create a gradient based on x position
   
   if( mouseX < width/2){ //relax state  
    //size should start large, become small at center
       rectSize = map( mouseX, 0, width/2, sizeMax, sizeMin);
    //radius should start at max, become 0 at center
      radius = map( mouseX, 0, width/2, sizeMax/2, 0);
   }
   if( mouseX > width/2){ //stress state
   //size starts small gets larger at right edge
       rectSize = map( mouseX, width/2, width, sizeMin, sizeMax);
   //radius should start at 0 at center, get 'sharper' at right edge
       radius = map( mouseX, width/2, width, 0, -sizeMax/2);
   }
   
   rect( mouseX,mouseY, rectSize, rectSize, radius); //draw the shape
};


```

