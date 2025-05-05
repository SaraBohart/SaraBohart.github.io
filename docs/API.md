---
title: API
tags:
- tag1
- tag2
---
## Standard Message structure
Byte 1|Byte 2|Byte 3|Byte 4|Byte 5|Byte 6|Byte 7|Byte 8|
------|------|------|------|------|------|------|------|
A|Z|Sender Initial|Receiver Initial|Data 1|Data 2|Y|B|
 <br>

Note: Data 2 does not exist in some messages. A message containing one data point would look like this. <br>

Byte 1|Byte 2|Byte 3|Byte 4|Byte 5|Byte 6|Byte 7|
------|------|------|------|------|------|------|
A|Z|Sender Initial|Receiver Initial|Data 1|Y|B|
<br>
The message handeling code is designed to notice the start sequence, AZ, and look at the subsequent characters until it notices that the string is too long, or it reaches the end sequence, YB. It will either pass, destroy, or filter that data based on if the receiver initial is B. Depending on the initials, the code will filter out data that contains invalid characters for that message.
<br>
The initials for all of my team are shown bellow. <br>

Member|Initial|
------|-------|
Xander|H|
Ella|G|
Julia|S|
Sara (me)|B|
<br>
Our team decided to use our last initials so the X could be used for global massages, as per the project requierments.

## Messages
The following tables show what data my system receives from or sends to each team member. 
### From Xander
&nbsp;|Byte 5|Byte 6|
------|------|------|
Name|ChangeDirection|ChangeSpeed|
Type|char|char        |
Min|0|1|
Max|1|8|
Example|1|5|
Use|From HMI to select a planet|From Direct drive mode to set direction|

An example of what this message could look like is AZHB03YB, which means that the motor will spin in the forward direction at the speed asociated with the moon. This would write the three logic pins (B1,B2,B3) to the sequence that represents the moon. This tells the SPI microcontroller to turn the motor on and off at the appropriate interval to generate the RPM needed to emulate the moon's gravity.

While the final design of our system does not include functionality for the motor moving in reverse, this could be implemented in the future by adding another logic pin that turns on when the direction flips.

### To Ella
&nbsp;|Byte 5|
------|------|
Name|ChangeSpeed|
Type|char|
Min|1|
Max|8|
Example|5|
Use|To WiFi to communicate current RPM|

An example of what this message would look like is AZBG7YB, which means the selected planet is Neptune and the motor is spinning at that speed.

### From Julia
&nbsp;|Byte 5|
------|------|
Name    |CheckDistance|
Type    |char     |
Min     |0            |
Max     |1            |
Example |1            |
Use|From sensor to check for safety|

An example of what this message could look like is AZSB0YB, which would mean that it is not safe to opporate the motor. In this case, the logic pin for the motor spinning would be written low, keeping the motor still.

## Code
The code for the message handeling can be found [here](https://github.com/user-attachments/files/20009027/MessageTest2.zip). <br>
This code identifies the start of the message by detecting an A followed by a Z. It then identifies the sender and receiver, checking if they are in the team and if they are me. If they are not in the team or I am the sender, the message is deleted. If not, the sender is identified and their data is stored in the associated variable. <br>
The ChangeSpeed and CheckDistance variables write GPIO pins high or low to indicate their state. The CheckDistance variable is a simple on or off for a one or zero respectively. The ChangeSpeed Variable turn a pattern of three pins on and off to select the planet. These patterns are shown in the following table.<br>

ChangeSpeed value|Planet|B1|B2|B3|
-----------------|------|----|----|----|
1|Mercury|On|On|On|
2|Venus|On|Off|Off|
3|The Moon|Off|On|Off|
4|Mars|Off|Off|On|
5|Jupiter|On|On|Off|
6|Saturn|Off|On|On|
7|Neptune|On|Off|On|
8|Pluto|Off|Off|Off|

The code that reads that logic and modulated the motor speed can be found [here](https://github.com/user-attachments/files/20009046/AdvancedSerialCom.zip).<br>
For debugging, turn on the redirect printf to UART option for EUSART1. This allows the program to print the error messages. These error messages cause lag when the system is plugged in to the whole project. For the best functionality, ensure that the redirect printf to UART option is NOT selected for EUSART1.
