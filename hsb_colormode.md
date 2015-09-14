#HSB Color Mode

The Processing HSB colormode provides a powerful option for using color as design features in our programs.  When working with RGB colors, it can be difficult to determine how to modify an RGB value using code, for example how can we modify an RGB value to get a slightly darker shade of the current fill color?  However, The HSB colormode allows programmatic control over the Hue, Saturation, and Brightness of colors. For example, a user-interaction can be used to trigger a decrease in Brightness, as an easy way add hover-type behaviors to button shapes. 

![](HSB_Cone.png)

Image from: [TomJewett.com](http://www.tomjewett.com/colors/hsb.html)

###Color Wheel
To create a simple color-wheel, we can use the arc() function, in conjunction with the HSB colorMode().

The *Processing.js* ``arc()`` function takes 6 parameters: x, y, w, h, startDegree, endDegree.  In the Khan Academy, all angles use degree measurement as the default, while for other *Processing.org* programs, radians is the default angular measurement mode. So, in the jsbin code example, all angle measurements are wrapped in the ``radians( )`` function to convert our angle degree value into the equivalent radians value.


```
//Let's make a color wheel by mapping HSB values to arc() //segments that are positioned radially around the center.
//HSB colors represent a color wheel with 0 degrees=red, 120 //degrees=green, 240 degrees=blue
//we need to match the arc startDegree to the correct HSB 
//hue value, where the HSB hue values range from 0 to 255
//For example: we want green color at 120 degrees 
//with a hue value of 120/360 => (1/3)*255
//we'll create variables to represent these values

//setup
colorMode(HSB);
background(0, 0, 255);
noStroke();

//declare and initialize variables
var hueValue=0;  //the current color of the hueValue, will modified to map to the current HSB.
var startDegree=0;  //the arc parameter that starts the arc, will be modified to draw new arcs
var angleSlice=60; //the degree 'width' of each arc.  How much each arc is offset from the previous arc
var endDegree=angleSlice; //the endpoint for an arc, the offset of size 'angleSlice', from the arc startDegree.
translate(200,200);  //move the origin to the center of the canvas


//using initialized values  Create first arc which is red
fill(hueValue, 255, 255);
//arc(x,y,w,h,start,stop)
arc(0,0,300,300,startDegree,endDegree); //first arc
//begin incrementing startDegree, endDegree, and hueValue


while( startDegree <360 ){
 
startDegree=startDegree+angleSlice;  //termination, we know that startDegree keeps incrementing and will eventually be larger than 360
endDegree=endDegree+angleSlice;
hueValue=(startDegree / 360) * 255;
// keep changing hue value, use that to color each arc
fill(hueValue, 255, 255);
//arc(x,y,w,h,start,stop)
arc(0,0,300,300,startDegree,endDegree); //first arc
    
}
```

<a class="jsbin-embed" href="http://jsbin.com/boxepu/embed?js,output">JS Bin on jsbin.com</a><script src="http://static.jsbin.com/js/embed.min.js?3.34.3"></script>