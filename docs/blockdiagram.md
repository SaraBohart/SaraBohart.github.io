---
title: Block Diagram
tags:
- tag1
- tag2
---
This block diagram is for the actuator subsystem. It will use a digital motor driver to change the speed of the motor based on data from the distance sensor.
## Individual Block Diagram
![SaraBohartBlockDigramMotor drawio (4)](https://github.com/user-attachments/assets/2c7853fb-b3d5-4b63-83ab-6c8d1916eebb)

Updated 5/1/25
## Functionality
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

## Decision Making Process
The final design of my system was 

## Adhearance to Product Requirements
My final system utilizes an SPI motor driver to control the speed of the motor. The driver I chose has a pinout for PWM control, which would have been more straightforward for the planetary centrifuge. However, the speed was not modulated using PWM, but rather SPI whriting the pin high and low in an interval that acted as a duty cycle, albeit very slow. This fulfils the product requierment for a serial actuator.
This system also utilizes the PIC18F47Q10, which is a PIC microcontroller. It was required that all teams have atleast one PIC and one ESP. As the rest of my teammates are using the ESP-32, my system satifies the PIC requierment. 
My system uses 8 pin headers to share power, ground, and UART RX and TX between two of the three other boards in my team. This satisfies the UART Daisy Chain requierment. 
Almost all of the parts in my final system are offered as surface mounts. In my final PCB design, the motor and the bullet connector are the only non surface mount parts, because the motor cannot be surface mounted and the bullet connectors from class were throughhole. 
The system has a switching regulator for each PIC used. It could be plugged in to the 9V power supply, but doing so would lower the power of the motor, which is why we went with a 12 volt 2 amp power supply. In the final PCB design, the jumpers to connect and disconnect the power sources have been replaced with fuse holders. This is because if we are to have this project in a museum, I do not expect the museum staff to need those jumpers. I beleive they would benifit more from the protection that the fuses would grant than the flexability they would get from the jumpers. 
The in circuit programming circuitry is provided as headers that the snap programmer can plug into.
