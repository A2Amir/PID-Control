# Introduction

Control is how we use the steering, throttle, and breaks to move a car where we want it to go. Control's a trickier problem than it might seem when human turns through an intersection, we use our intuition and experience to determine how hard to steer and when to accelerate and whether we ever need to step on the brakes. Teaching a computer how to do this is hard.
Control algorithms are often called controllers and one of the most common and fundamental controllers is the PID controller. In this lesson, you will learn how to implement a PID controller in Python then, we will dive into the Udacity simulator to implement a PID controller in C++.

# PID Control

PID control is a vast field in control and many classes can be taught about this one subject matter. I'll give you the very basics so that you can be able to drive a car around and the Google car to the present day uses a version of this exact same controller but much more tuned.


Below is presented the problem. Consider the car in the image below with a steerable front axle and 2 non-steerable wheels in the back. Say we wished this car to drive along the black line (the so-called reference trajectory) and assume the car has a fixed forward velocity but you have the ability to set the steering angle of the car. How would you do this? 

1.	You could set the steering angle in proportion to what is known as the "Cross Track Error", which is the lateral distance between the vehicle and the so-called reference trajectory.
2.	You could use a steering constant.
3.	You could use random steering commands


<p align="right"> <img src="./img/1.png" style="right;" alt=" the maze " width="450" height="230"> </p> 

You will reach the trajectory, which means the larger the error, the more you're willing to turn towards the target trajectory.
Proportional Control
What you just learned above is called a "P-controller" where P stands for proportional. Suppose you steer in proportion to the cross track error and your steering angle is proportional to the cross Track error by a factor Tau. What will happen to the car?

1.	It never quite reaches the reference trajectory?
2.	It overshoots?
3.	Either can happen?


<p align="right"> <img src="./img/2.png" style="right;" alt=" the maze " width="450" height="230"> </p> 
