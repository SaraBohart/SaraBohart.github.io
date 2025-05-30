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
Option 1|Pros|Cons|
----------|----|----|
![Image of Motor option 1](https://github.com/user-attachments/assets/6ea4ea9f-ae1e-49a3-9477-d736d1bb7b94) <br> 381-3642-ND <br> GEARMOTOR 150 RPM 24V PLANETARY <br> Individual Cost: $475.38 <br> [DigiKey](https://www.digikey.com/en/products/detail/ebm-papst-inc/VG-VD4915BK1-P63-2-30/9598045) | RPM - This motor is rated for 150 RPM which is the fastest we will need the motor to go. <br> Torque - The torque rating of 7050 mNm is more than enough to spin the centrifuge.|Expensive - The budget is $60 per team member ($240 for the whole team) and I am not able to pay for this out of pocket. <br> Lead Time - The Manufacturer Standard Lead Time is listed as 16 weeks, which is too long for the project to wait.|

Option 2|Pros|Cons|
----------|----|----|
![Image of Motor option 2](https://github.com/user-attachments/assets/47ec94f5-9dc7-471b-86b4-758c30d06072)942-PAN14EE12MD-ND <br> STANDARD MTR DC BRUSH 300MM LEAD <br> Individual Cost: $4.75 <br> [DigiKey](https://www.digikey.com/en/products/detail/nmb-technologies-corporation/PAN14EE12MD/6035766) |Wire Leads - These will make it easier to connect the motor to the system than if the motor came with an encoder and all the terminals that come with that. <br> Torque - The torque rating is 4.9 mNm, which should be enough if the centrifuge is made of PLA. |Gear Train Needed - This motor is rated for 12800 RPM, so a significant gear reduction will be needed to get to the preferred speed. These gears would need to be sourced or 3D printed because the motor does not come with them. <br> Voltage - It needs 12V which is much higher than the 3.3 that the microcontroller uses.|

Option 3|Pros|Cons|
----------|----|----|
![Image of Motor option 3](https://github.com/user-attachments/assets/535469bf-c9b0-42f6-9837-c90bf3cc941a) PAN14EE12AA1 <br> STANDARD MOTOR 12850 RPM 12V <br> Individual Cost: $5.22 <br> [DigiKey](https://www.digikey.com/en/products/detail/nmb-technologies-corporation/PAN14EE12AA1/2417070) |Torque - The data sheet indicates that this motor can work with 4.9 mNm, which should be enough for our centrifuge. <br> Cost - This motor is very cost effective as it only costs $5.22.|Gear Train Needed - This motor is rated for 12850 RPM, so a gear reduction will be needed. These gears would need to be sourced or 3D printed because the motor does not come with them. <br> Voltage - This motor also takes 12V, which will require a second power source.|

Option 4|Pros|Cons|
----------|----|----|
![Image of Motor option 4](https://github.com/user-attachments/assets/30ba0258-de9e-4d76-901e-75019b081028) 25SG-370CA <br>6V 25D Metal Gearmotor, 280rpm <br>Individual Cost: $6.58 <br> [RoboShop](https://www.robotshop.com/products/e-s-motor-6v-25d-metal-gearmotor-280rpm?pr_prod_strat=e5_desc&pr_rec_id=40bbe8f7d&pr_rec_pid=7487431409825&pr_ref_pid=7487467978913&pr_seq=uniform)|Cost - For a gear motor this is not very expencive. <br> Comes with mounting - There is an aluminum mount for the shaft and mounting holes to attach the motor to the project. |New Vendor - This motor would require another order form because it is not from digikey <br> Lack of datasheet - The only specs given are on the vendor's cite <br>Shipping fee - The shipping fee is estimated to be at least $16.50|

Option 5|Pros|Cons|
--------|----|----|
![image of motor option 5](https://github.com/user-attachments/assets/5040106f-0937-45a9-ba16-5b30dc655c21) Brushed 12V DC Gear Motor <br>0.27Kg.cm/465RPM w/ 22.56:1 Planetary Gearbox <br> Individual Cost: $10.75 <br> [StepperOnline](https://www.omc-stepperonline.com/brushed-12v-dc-gear-motor-0-27kg-cm-465rpm-w-22-56-1-planetary-gearbox-pa22-201213500-g23)|Good RPM - RPM is near what we need for this project <br> Low cost <br> Close approximation to the motor we ended up using|Another Vender - This would increase shipping costs|


### Selection
Option 4 <br>
The best choice for this project is the 6V 25D Metal Gearmotor because it has a high torque and a low speed. The motor only needs to run at 150 RPM, and this motor has a max rated speed of 280 RPM. It is also cost effective despite the shipping fee.<br>
Note: While this was the selected motor, it never arrived in the mail, so our team is using another 12V DC motor that was found in a bag of extra motors. Option 5 was added as a close approximation to what that motor was, as the actual motor could not be identified.

## Switching Power Supply
### Requierments
The switching voltage regulator must output 3.3 V from a 12 V source. 
### Options
Option 1|Pros|Cons|
----------|----|----|
![Switching Regulator Option 1](https://github.com/user-attachments/assets/83e569cc-354f-4664-b740-2c4536e540f7) <br> LM2655MTCX-3.3 <br> IC REG BUCK 3.3V 2.5A 16TSSOP <br> Individual Cost: $1.19 <br> [DigikKey](https://www.digikey.com/en/products/detail/rochester-electronics-llc/LM2655MTCX-3-3/12600721)|Rated for 12 V - This chip can operate between 4 and 14 V, which is in range of what the motor requires <br> Fixed 3.3 V Output - The chip has a fixed output of 3.3, meaning no matter what, the microcontroller will receive 3.3 V. |Shipping Fee - The shipping fee for this chip is $8 because it is a marketplace product. <br> Only one output - There is only one output, so all 3.3 V power will be drawn from the single pin. |

Option 2|Pros|Cons|
----------|----|----|
![Switching Regulator Option 2](https://github.com/user-attachments/assets/0c30a12a-19e6-4f21-a0c8-68c906158751) <br> LM2655MTC-3.3/NOPB <br> IC REG BUCK 3.3V 2.5A 16TSSOP <br> Individual Cost: $4.66 <br> [DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/LM2655MTC-3-3-NOPB/363755)|Texas Instruments - This is a big name manufacturer that can be trusted. <br> No Shipping fee - There is no additional shipping fee. <br> Same Ratings - This part has the same ratings as option 1.|Expensive - Despite having the same ratings as option 1, this chip is significantly more expensive. <br> Many pins - This chip has a lot of small pins that need to be soldered very carefully without overheating the chip.|

Option 3|Pros|Cons|
----------|----|----|
![Switching Regulator Option 3](https://github.com/user-attachments/assets/1886759d-2b37-4d81-8f2f-49cedb9dd008) <br> LM2651MTCX-3.3/NOPB <br> IC REG BUCK 3.3V 1.5A 16TSSOP <br> Individual Cost: $3.93 <br> [DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/LM2651MTCX-3-3-NOPB/366869)|Low Cost - It costs less than the previous Texas Instruments part <br> Datasheet - This chip comes with a datasheet.|Less Power - THe previous options offered 2.5 A while this one only gets 1.5 A <br> Buying on scale - This chip is more expensive than option 1 when buying 4.|

Option 4|Pros|Cons|
----------|----|----|
![Screenshot 2025-02-20 160933](https://github.com/user-attachments/assets/a97830bc-183c-40a6-b805-0942c42c4421)<br> LM2576-3.3WU <br> IC REG BUCK 3.3V 3A TO263-5 <br> Individual Cost: $1.75 <br> [DigiKey](https://www.digikey.com/en/products/detail/microchip-technology/LM2576-3-3WU/1027681) |Low Cost - only $1.75 each.<br>Current Output - the output current is 3A which is enough for the components this is powering.|Fixed output - This part can only do 3.3V out. <br>Minimum Circuit - the minimum circuit includes an inductor and a diode, which I will need to find and buy|

### Selection
Option 4 <br>
Option 4 is cost effective, simple, and overall the best option. I have also used a similar component before, so it will be familiar to work with. 

## Motor Driver
### Requierments
The motor driver must use eirthe SPI or I2C communication per the project requierments.
### Options
Option 1|Pros|Cons|
----------|----|----|
![Motor Driver Option 1](https://github.com/user-attachments/assets/15862760-4163-4db0-8e28-1f16d2803363) <br> IFX9201SGAUMA1 <br> IC HALF BRIDGE DRIVER 6A 12DSO <br> Individual Cost: $3.68 <br> [DigiKey](https://www.digikey.com/en/products/detail/infineon-technologies/IFX9201SGAUMA1/5415560?gclsrc=aw.ds&&utm_adgroup=&utm_source=google&utm_medium=cpc&utm_campaign=PMax%20Shopping_Product_Medium%20ROAS%20Categories&utm_term=&utm_content=&utm_id=go_cmp-20223376311_adg-_ad-__dev-c_ext-_prd-5415560_sig-Cj0KCQiA-5a9BhCBARIsACwMkJ6eR_NkTtW9b4WwyVvB6PQpvB989ygKcRpoiPeZjfR2-aoemkHsjqAaAlCVEALw_wcB&gad_source=1&gclid=Cj0KCQiA-5a9BhCBARIsACwMkJ6eR_NkTtW9b4WwyVvB6PQpvB989ygKcRpoiPeZjfR2-aoemkHsjqAaAlCVEALw_wcB&gclsrc=aw.ds) |In Class Example - This is the chip that we use in class, so there are plenty of resources I can use for this device. <br> Supply Voltage Range - The chip requires 5-36 V, which includes 12 V, so no new regulator is needed.|Supply Voltage Range - 3.3 V is too low for this cip, so It could not pull power from the voltage regulator. <br> Too many features - This chip has the capacity to be controlled by PWM, but the project requires that only I2C or SPI are used.|

Option 2|Pros|Cons|
----------|----|----|
![Motor Driver Option 2](https://github.com/user-attachments/assets/ce842184-4fc4-433f-be93-381d6b27d00f) <br> NCV7703CD2R2G <br> IC HALF BRIDGE DRVR 1.1A 14SOIC <br> Individual Cost: $3.60 <br>  [DigiKey](https://www.digikey.com/en/products/detail/onsemi/NCV7703CD2R2G/7325621)|Supply Voltage - The supply voltage range is 3.15 - 5.25 V, so this chip can operate on the 3.3 V regulator. <br> Only uses Serial Communication - There is no other option than what is required by the project.|New chip - THis chip is not used in the class, so new bugs will be harder to address. <br> Lead Time - The Manufacturer Standard Lead TIme is 33 Weeks, so if DigiKey runs out of this part before we purchase it, the team will not be able to use this part.|

Option 3|Pros|Cons|
----------|----|----|
![Motor Driver Option 3](https://github.com/user-attachments/assets/349d41eb-22a5-4fdc-8b02-cdc659e0921e) <br> NCP51530BDR2G <br> Half Bridge (2) Driver General Purpose Power MOSFET 8-SOIC <br> Individual Cost: $2.23 <br> [DigiKey](https://www.digikey.com/en/products/detail/onsemi/NCP51530BDR2G/8636481)|Cost - This is the least expensive of the researched motor drivers. <br> Supply Voltage - This chip can run on the 12 V rail.|Very Short Datasheet - The datasheet is very short and does not have as much information as the other chips <br> Pin Names - Pin Names are different from those used in the class, so translating learning will be a step more difficult.|

### Selection
Option 1 <br>
This is the best choice because it is the same one from the class, theirfore there are more resources readily avalible to me for debugging and troubleshooting.

## Microcontroler
### Requierments
The microcontroler needs to support the selected motor driver and communicate through UART with the sensor and the OLED systems. To accomplish this, it will need one UART and one I2C subsystem. This will be a total of 4 pins 2 for I2C and 2 for UART RX and TX.
### PIC 
PIC Info|Answer|Notes|
----------|----|----|
Model|PIC18F47Q10-I/PT| |
Product Page|[Microchip](https://www.microchipdirect.com/product/PIC18F47Q10-I/PT?productLoaded=true)| |
Datasheet|[PDF of the Datasheet](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://ww1.microchip.com/downloads/aemDocuments/documents/MCU08/ProductDocuments/DataSheets/PIC18F27-47Q10-Micorcontroller-Data-Sheet-DS40002043.pdf)| |
Application Notes|[UART](https://www.microchip.com/en-us/application-notes/tb3282) <br> [Serial EEPROMs](https://www.microchip.com/en-us/application-notes/an2045)|It did not have application notes on I2C but it is the same family as the in-class PIC, so that should transfer over enough.|
Vendor Link|[DigiKey](https://www.digikey.com/en/products/detail/microchip-technology/PIC18F47Q10-I-PT/10187786)|Can ship immedeately|
Code Examples|[All code examples from Microchip](https://mplabxpress.microchip.com/mplabcloud/example?device=q10) <br> [I2C Host write data](https://github.com/microchip-pic-avr-examples/pic18f47q10-cnano-i2c-write-bare/tree/1.0.4)||
External Resources|[I2C coding tutorial](https://www.youtube.com/watch?v=8Kv0by_8SJE) <br> [Got I2C Working!](https://www.youtube.com/watch?v=gONuL7G5XiY) <br> [Implemetning I2C on PIC](https://www.youtube.com/watch?v=lpwyGVEdt0Q&pp=ygUGI2NpMmNp)||
Unit cost|$1.65||
Absolute Maximum Current|350 mA|It is the highest current any pin can take|
Supply Voltage Range|-0.3 to +6.5 V|To VDD pin|
Maximum GPIO Current per pin|50 mA|Positive or negative|
Supports External Interrupts?|Yes|They are mentioned in the Datasheet section 15.8.
Required Programming Hardware, Cost|ESP32|No cost because one came with the class
Works with MPLabX?|Yes||
Works with Microchip Code Configurator?|Yes||

### Pins
Module|# Available|Needed|Associated Pins|
------|-----------|------|---------------|
GPIO|35|0|All Pins|
UART|16|2|RB0-7, RC0-7|
I2C|16|2|RB0-7, RC0-7|
Reset|1|1|RE3|
OSC|1|0|RA6|

### My Role
My role as a team member is to plan and lead meetings to ensure that we are staying on track as a group. My section of the project is the actuator system. I need to design something that takes information from the distance sensor, uses that information to pick a spin speed, drives a motor to spin at that speed, and communicate that speed with the OLED system. 

### MPLABX Project
This is a screenshot of my MPLABX project for the microcontroller in charge of the message handeling.
![API Chip Pinout image](https://github.com/user-attachments/assets/9ffa2c05-17ba-41ec-baab-6258988319cb)

This is a screenshot of my MPLABX project for the microcontroller in charge of the SPI motor driver.
![SPI Chip Pinout image](https://github.com/user-attachments/assets/65df1968-cdb7-412a-a03b-ca3b6fad73e2)

### Selection
I used two of the same PIC18F47Q10-I/PT microcontrollers. Two were necisarry to handel all of the functionality I needed for this priject. This chip was ideal because it was the same one used in class, meaning I had access to may resources to help trouble shoot and debug my code.

## Final Major Components
Component|Quantity|Required Subcomponents|Use|
---------|--------|----------------------|-----------------------|
![image of motor option 5](https://github.com/user-attachments/assets/5040106f-0937-45a9-ba16-5b30dc655c21) Brushed 12V DC Gear Motor|1|None|Spinning the centrifuge|
![Screenshot 2025-02-20 160933](https://github.com/user-attachments/assets/a97830bc-183c-40a6-b805-0942c42c4421)<br> LM2576-3.3WU |2|330uH Inductor <br> 330uF Capacitor <br> 1N5822 Diode <br> 100uF Capacitor|Stepping down the input voltage to 3.3 V for the logic power|
![Motor Driver Option 1](https://github.com/user-attachments/assets/15862760-4163-4db0-8e28-1f16d2803363) <br> IFX9201SGAUMA1|1|2 <33uF Capacitors|Controling the direction and power to the motor|
![PIC18F47Q10 image](https://github.com/user-attachments/assets/72d89ae4-0f2f-4dd1-9c2d-b88c178762c5) PIC18F47Q10-I/PT|2|220 ohm resistor|Handeling the UART Messages and SPI motor driver|
8 pin Ribbon Cable Connector (Supplied in class)|2|None|Connecting to the other systems|
Bullet Connecctor (Supplied in class)|1|None|Connecting to the power source|
12V 2A Power Source|1|None|Powering the system|
