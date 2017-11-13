#Time

Processing has several different functions that can be used in programs.  

    millis( ) // gives time elapsed since the program started in milliseconds where there are 1000 milliseconds  in 1 second.
    
    seconds( ), minutes(), hours(), etc //provides actual time according to the computer's clock
    
    
###Timer
To create a timer, you can use an elapsed time calculation where you create a variable at the beginning of the program and initialize it with one of the time functions, then check to see the difference between current time and the startTime variable, reset the startTime variable when the timer has reset.



```java
    var initialTime = millis(); //called once at beginning

    var draw=function(){
    var elapsedTime = millis() - initialTime;
    if (elapsedTime > 3000){ // 3 seconds has passed
       println("3 seconds");
    initialTime = millis(); //reset initial time
    }
};
```

