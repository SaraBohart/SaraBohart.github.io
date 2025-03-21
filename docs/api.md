---
title: API
tags:
- tag1
- tag2
---
## Messages
&nbsp;|Byte 1|Byte 2|Byte 3|Byte 4|
------|------|------|------|------|
Name|ChangeSpeed|CheckDistance|ChangeDirection|MotorSpeed|
Type|int16_t|uint16_t|int16_t|int16_t|
Min|1|0|0|-200|
Max|9|1|1|200|
Example|5|1|0|150|
Use|From HMI to select a planet|From sensor to check for safety|From Direct drive mode to set direction|To WiFi to communicate current RPM|

## Code
[APIDraft1.zip](https://github.com/user-attachments/files/19398071/APIDraft1.zip) <br>
This is the first draft of my message processing code. It is untested, but it should receive a uart string, test if the string is compliant with the expected structure, and extract the correct information based on where it lies in the string. Then it should write a string containing the current RPM of the motor amd send it over uart.
