# Project - Wall Bouncing Robot

This is the first project in Robotics 1 class. In this project, we will make a Roomba-like robot. The robot is expected to maneuver in a closed room without hitting the walls. The outcomes of this project are expected as follows:
- Build a mobile robot with processors, actuators and sensors that are introduced in the class.
- Write Python code to realize the wall bouncing robot (Feel free to write your code from scratch or start from [`wall_bouncer.py`](https://github.com/linzhangUCA/project_template-wall_bouncer/blob/main/wall_bouncer.py)).
- Figure out a way to automatically launch the robot after booting up the RaspberryPi. Briefly describe your automatic startup approach or upload the script you used.  
- Complete a project report using this file ([`README.md`](https://github.com/linzhangUCA/project_template-wall_bouncer/blob/main/README.md)).
- Upload a video for demonstration (Unfortunately, you may need to compress your video before uploading).

## Workflow
3 LEDs (GREEN, YELLOW, RED), 1 button, (at least) 1 ultrasonic distance sensor and 2 motor drivers are needed. [gpiozero](https://gpiozero.readthedocs.io/en/stable/) library is highly recommended for your coding.
1. Enable the motors. Confirm the motors are enabled (check GPIO pins voltage level). 
2. Robot entering **Pausing** mode. Set the GREEN LED to be a dimmer (PWM). Make sure robot's motion is stopped in this mode.
3. Press the button to enable the **Playing** mode. Robot should be able to move forward. Light up GREEN LED and keep the brightness a constant. Use the distance sensor (Feel free to use more than one) to monitor walls in front of the robot. Turn the robot away from the approaching wall within a certain distance.
4. Press the button again will be able to switch the mode back to **Pausing**. Pressing the button later on can switch the mode back and forth. 

Record time consumption in **Playing** mode, once over 60 seconds, light up YELLOW LED. If over 90 seconds, turn off the robot and blink (turn on then turn off) the RED LED 10 times, then shut down the whole system.

## Summary
> Write below to complete this report. You may want to read the [Markdown guide](https://guides.github.com/features/mastering-markdown/) to better format this report.
- The first project in Robotics 1 we were tasked with taking our basic one direction robot and make it like a Roomba robot. This meant that we were expected to travel around a room without hitting any objects or walls. I approached this with a python code that allowed me to time certain stages of the robot being on and eventually shut off after 90 seconds. I found a tutorial on line that showed me how to start up my Pie and run a certain code with a button push, this simulated the Roomba being turned on with a button push. Next I installed the distance sensor and tested my robot in an arena, the robot ran smack into the wall, so I had to edit some of the code to make it drive slower. This fixed some of the issues, but when the robot headed for a corner it did not have enough space or time to correct and not hit the wall. I then decided to give my robot a little more of a peripheral view by adding two more distance sensors that were angled to the front corners of the robot. There was some conflict with pins that I saldered, so by the end of the project I only had two angled sensors and one LED light to signify the status.
### Material List
> Please list hardware (better with links) used in this project below.  
1. 3 HC-SR04 distance sensors - The datasheet can be referenced [here](https://www.digikey.com/htmldatasheets/production/1979760/0/0/1/hc-sr04.html?utm_adgroup=xGeneral&utm_source=google&utm_medium=cpc&utm_campaign=Dynamic%20Search_EN_Product&utm_term=&utm_content=xGeneral&gclid=Cj0KCQiAtJeNBhCVARIsANJUJ2FJg9IsgiI7bnsw0c3iY6SEr15C9du0w1hiRknYCaaOv6_ynUiBACkaAi8oEALw_wcB)
2. Dual motor driver board - MC 33926 The datasheet can be referenced [here](https://www.pololu.com/product/1212)
3. Raspberry Pi- The datasheet can be referenced [here](https://www.pololu.com/product/2797)
### Software List
> Please list and briefly describe the Python libraries and any software used to realize the robot.
Python class PhaseEnableRobot was used for powering the motors.
### Usage
> Briefly describe how to use this robot. Imagine you are teaching a person how to use your robot.
This robot is a push button start Roomba like robot. It has two motors powering a wheel on each side with a ball roller in the front. It uses distance sensors to avoid objects by turning away from them. 

