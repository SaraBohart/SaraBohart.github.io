---
title: Block Diagram
tags:
- tag1
- tag2
---
This block diagram is for the actuator subsystem. It will use a digital motor driver to change the speed of the motor based on data from the distance sensor.
## Individual Block Diagram
![SaraBohartBlockDigramMotor](https://github.com/user-attachments/assets/39dbad65-09cf-474b-b4d8-5e8a20ab6f98)
Updated 5/1/25
## The Plan
The project that this system is designed for is emulating the gravity of different planets using a centrifuge. I am in charge of the motor, which needs to get information from the distance sensor and the HMI to know if it is safe to spin and how fast to spin the motor to emulate the selected gravity. <br>
All of the message handeling and SPI code cannot run on one microcontroller, so a second one was added. They each are powered by their own voltage regulator, and communicate over a logic gate to control the motor speed. B0 sets the motor on or off based on sensor input and B1-3 select the planet. <br>

|Setting|B0|B1|B2|B3|
|-------|---|---|---|---|
|Off for safety|low|either|either|either|
|Mercury|either|high|high|high|
|Venus|either|high|low|low|
|Moon|either|low|high|low|
|Mars|either|low|low|high|
|Jupiter|either|high|high|low|
|Saturn|either|low|high|high|
|Neptune|either|high|low|high|
|Pluto|either|low|low|low|

<br>
This then trigers the SPI to switch on and off for different intervals, creating a PWM signal to modulate the speed of the motor. The motor will only spin when B0 is written high, because that indicates that it is safe to do so. <br>
For the purposes of demonstration, the logic gate will be displayed using LEDs on a breadboard. In the official project, the wires will jump directly between the PICs.
