---
title: Block Diagram
tags:
- tag1
- tag2
---
This block diagram is for the actuator subsystem. It will use a digital motor driver to change the speed of the motor based on data from the distance sensor.
## Individual Block Diagram
![SaraBohartBlockDigramMotor](https://github.com/user-attachments/assets/023b9ee4-2995-48d3-88bd-a9fecb1da387)
## The Plan
The project that this system is designed for is emulating the gravity of different planets using a centrifuge. I am in charge of the motor, which needs to get information from the distance sensor to know how fast to spin the motor to emulate the selected gravity. It will also share the current PWM value with the OLED so it can calculate and display the centrifugal force that the motor is causing.  
Per the project requirements, the motor must communicate with the microcontroller through an “complex motor driver IC”. I have decided to use the IFX9201SGAUMA1 from Infineon Technologies because we are also using that component in class. This will remove a layer of complexity, allowing me more time to focus on other areas of the course and the project, and save some money as my team will not have to buy as many parts. For the same reason, the microcontroller I have chosen is the DIP version of the PIC18F47Q10. Since both of these components are used in the class, our team saves time and money, which can be used on other aspects of the project.  
More research needs to be done on gravity emulation. I need to know how the size of the centrifuge will affect the power required from the motor. Once those calculations are done, the motor will be placed as shown in the block diagram. It will be controlled by the motor driver, which is controlled by the microcontroller, which is responding to input from the distance sensor.
