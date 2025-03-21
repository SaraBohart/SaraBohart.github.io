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
