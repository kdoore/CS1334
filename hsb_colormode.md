#HSB Color Mode

The Processing HSB colormode provides a powerful option for using color as design features in our programs.  When working with RGB colors, it can be difficult to determine how to modify an RGB value using code, for example how can we modify an RGB value to get a slightly darker shade of the current fill color?  However, The HSB colormode allows programmatic control over the Hue, Saturation, and Brightness of colors. For example, a user-interaction can be used to trigger a decrease in Brightness, as an easy way add hover-type behaviors to button shapes. 

###HSB Colors
The image below shows the HSB colorspace.  From this diagram, we can see that if we want to understand a specific HSB color, given in terms of Hue, Saturation, and Brightness parameter values, it is easiest to read a HSB color starting with the brightness parameter.  
###Brightness
The brightness scale defines grayscale colors, where a brightness value of 0 corresponds to black, and the max- brightness corresponds to white.  So, if we see an HSB value with O for brightness, the other values don't impact the color because the colorspace is at the lowest tip of the cone, black is the only color in this region.  So for a fill() function with 3 values fill(H, S, B), we should start reading the color from the right-most parameter, the B value.  If the B value is 255 (the max value), then we can see that these colors correspond to the top surface-edge of the cone.  
###Saturation
Within this circular slice, we can see that the center of the circle is white, and as the radius increases, the saturation increases so the outer rim of the circle has full saturation values.  So, when analyzing an HSB value, once we've determined that B is greater than 0, we next need to look at the S value to determine the saturation level.  This corresponds to moving outwards from the centerpoint of the circle, to colors with higher saturation intensity.  
###Hue
The hue value corresponds to the angle of rotation around the circle.  This image shows the hue angle incorrectly, for processing the hue values increase in the clockwise direction, with the 0 value at the 3 o'clock position. 

![](/assets/hsbColor.png)

Image from: [TomJewett.com](http://www.tomjewett.com/colors/hsb.html)

###Color Wheel
To create a simple color-wheel, we can use the arc() function, in conjunction with the HSB colorMode().

The *Processing.js* ``arc()`` function takes 6 parameters: x, y, w, h, startDegree, endDegree.  In the Khan Academy, all angles use degree measurement as the default input parameter.

![](/assets/Screen Shot 2019-01-09 at 5.54.10 PM.png)

```java

//setup configuration 

colorMode(HSB); 
//fill( Hue, Saturation, Brightness)

background(255); //white background
var angleSize = 45; //change using number scrubber
angleSize = constrain( angleSize, 1, 90); //make sure number is not 0 since it's used as a divisor

var startDegree = 0;
var numSlices = 360 / angleSize;
var hueValue = 0;

for( var i =0; i< numSlices; i++){
    hueValue = map( startDegree, 0, 360, 0,255);
    fill(hueValue, 255, 255);
    arc (200,200, 300, 300, startDegree, startDegree + angleSize );
    startDegree = startDegree + angleSize;
}

```
