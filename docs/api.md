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

### To Ella
&nbsp;|Byte 5|
------|------|
Name|MotorSpeed|
Type|int|
Min|-200|
Max|200|
Example|150|
Use|To WiFi to communicate current RPM|

### From Julia
&nbsp;|Byte 5|
------|------|
Name    |CheckDistance|
Type    |char     |
Min     |0            |
Max     |1            |
Example |1            |
Use|From sensor to check for safety|

## Code
[APIv3.zip](https://github.com/user-attachments/files/19558078/APIv3.zip) <br>
This is the first draft of my message processing code. It is untested, but it should receive a uart string, test if the string is compliant with the expected structure, and extract the correct information based on where it lies in the string. Then it should write a string containing the current RPM of the motor amd send it over uart. <br>
[UARTDebuggingAndViewing.zip](https://github.com/user-attachments/files/19558083/UARTDebuggingAndViewing.zip)<br>
This workspace allows you to see what the PIC is sending out over UART.
