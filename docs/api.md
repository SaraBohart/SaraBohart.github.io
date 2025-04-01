---
title: API
tags:
- tag1
- tag2
---
## Messages
### From Xander
&nbsp;|Byte 1|Byte 2|
------|------|------|
Name|ChangeDirection|ChangeSpeed|
Type|char|char        |
Min|0|1|
Max|1|9
Example|1|5|
Use|From HMI to select a planet|From Direct drive mode to set direction|

### To Ella
&nbsp;|Byte 1|
------|------|
Name|MotorSpeed|
Type|int|
Min|-200|
Max|200|
Example|150|
Use|To WiFi to communicate current RPM|

### From Julia
&nbsp;|Byte 1|
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
