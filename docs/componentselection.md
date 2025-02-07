---
title: Component Selection
tags:
- tag1
- tag2
---
## Motor
### Requirements 
The motor must be able to create an [RCF](https://www.sigmaaldrich.com/US/en/support/calculators-and-apps/g-force-calculator?srsltid=AfmBOop8NaSsvon0b_BEHic9ZCmkiujIRdpJg4A7WGM2Ohh8W5gX9p2s) that emulates the gravity of Jupiter (25.92 m/s^2 or 2.640 times the earth’s gravity according to [NASA](https://nssdc.gsfc.nasa.gov/planetary/factsheet/jupiterfact.html)). The Innovation Hub has 3D printers with build areas of 25x21x21 cm, so the projected radius of the centrifuge as of 2/7/25 is 10.5 cm. That means the motor must achieve a loaded speed of 150 RPM. The required torque is estimated to be 4.97 mNm. This changes depending on the shape of the centrifuge the team decides to use. This number assumes a 1 cm thick, solid, PLA disk.
### Options
Components|Pros|Cons|
----------|----|----|
![Image of Motor option 1](https://github.com/user-attachments/assets/6ea4ea9f-ae1e-49a3-9477-d736d1bb7b94) <br> 381-3642-ND <br> GEARMOTOR 150 RPM 24V PLANETARY <br> Individual Cost: $475.38 <br> [DigiKey](https://www.digikey.com/en/products/detail/ebm-papst-inc/VG-VD4915BK1-P63-2-30/9598045) | RPM - This motor is rated for 150 RPM which is the fastest we will need the motor to go. <br> Torque - The torque rating of 7050 mNm is more than enough to spin the centrifuge.|Expensive - The budget is $60 per team member ($240 for the whole team) and I am not able to pay for this out of pocket. <br> Lead Time - The Manufacturer Standard Lead Time is listed as 16 weeks, which is too long for the project to wait.|
![Image of Motor option 2](https://github.com/user-attachments/assets/47ec94f5-9dc7-471b-86b4-758c30d06072)942-PAN14EE12MD-ND <br> STANDARD MTR DC BRUSH 300MM LEAD <br> Individual Cost: $4.75 <br> [DigiKey](https://www.digikey.com/en/products/detail/nmb-technologies-corporation/PAN14EE12MD/6035766) |Wire Leads - These will make it easier to connect the motor to the system than if the motor came with an encoder and all the terminals that come with that. <br> Torque - The torque rating is 4.9 mNm, which should be enough if the centrifuge is made of PLA. |Gear Train Needed - This motor is rated for 12800 RPM, so a significant gear reduction will be needed to get to the preferred speed. These gears would need to be sourced or 3D printed because the motor does not come with them. <br> Voltage - It needs 12V which is much higher than the 3.3 that the microcontroller uses.|
![Screenshot 2025-02-07 155002](https://github.com/user-attachments/assets/535469bf-c9b0-42f6-9837-c90bf3cc941a) PAN14EE12AA1 <br> STANDARD MOTOR 12850 RPM 12V <br> Individual Cost: $5.22 <br> [DigiKey](https://www.digikey.com/en/products/detail/nmb-technologies-corporation/PAN14EE12AA1/2417070) |Torque - THe data sheet indicates that this motor can work with 4.9 mNm, which should be enough for our centrifuge. <br> Cost - This motor is very cost effective as it only costs $5.22.|Gear Train Needed - This motor is rated for 12850 RPM, so a gear reduction will be needed. These gears would need to be sourced or 3D printed because the motor does not come with them. <br> Voltage - This motor also takes 12V, which will require a second power source.|

### Selection
The best choice for this project is the 942-PAN14EE12MD-ND because it is the cheapest of the three and should be strong enough to power the centrifuge. While this motor will require 12V, the system can utilize a switching regulator that brings the voltage down to 3.3V for the other components.

## Switching Power Supply
### Requierments
The switching voltage regulator must output 3.3 V from a 12 V source. 
### Options
Components|Pros|Cons
----------|----|----

### Selection

## Motor Driver
### Requierments
The motor driver must use eirthe SPI or I2C communication per the project requierments.
### Options
Components|Pros|Cons
----------|----|----

### Selection

## Micro Controler
### Requierments
The micro controller must be compatable with the motor driver, use 3.3 volts, and have easily implementable code examples like the ones given in class.
### Options
Components|Pros|Cons
----------|----|----

### Selection

## Power Budget
Coming Soon!
