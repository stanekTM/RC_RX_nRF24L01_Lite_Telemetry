## Micro RX 2ch (motor driver)
RC receiver nRF24L01 with ATmega328P 5V/16Mhz processor for smaller dimensions.
It is possible to use Arduino Nano or Pro Mini. 
Telemetry sends the monitored voltage RX to TX. 
It includes CMT2150A transponder for laps timing and motor driver.
The motor driver IC is based on MX1208, MX1508, MX1515, MX1616L, TC1508S, SA8302 and others similar, using 4x pwm input control signals.
The possibility of setting the brake is in the code.
The firmware will be used for micro cars, boats, tanks and robots.

This RC receiver works with RC transmitters [OpenAVRc](https://github.com/stanekTM/OpenAVRc_Dev) or 
[Multiprotocol](https://github.com/stanekTM/DIY-Multiprotocol-TX-Module) from my fork.

Note: I use (Arduino) ATmega328P 5V/16Mhz and supply VCC only with 3.3V voltage. 
I haven't tried the 3.3V/8Mhz version yet. 
If you supply the VCC directly with a LiPo 1S cell, except for the nRF24L01, the analog voltage measurement will not work due to the VREF.
#
<a href="https://youtu.be/E0pgMNPuYU4"><img src="documents/youtube.PNG" width="640" /></a>

<img src="documents/Micro_RX_2ch_A1_Motor_Driver_0.jpg" width="276" /> <img src="documents/Micro_RX_2ch_A1_Motor_Driver_1.jpg" width="276" />
<img src="documents/Micro_RX_2ch_A1_Motor_Driver_2.jpg" width="276" />
<img src="documents/Micro_RX_2ch_A1_Motor_Driver_3.jpg" width="276" />
<img src="documents/Micro_RX_2ch_A1_Motor_Driver_4.jpg" width="276" />
<img src="documents/Micro_RX_2ch_A1_Motor_Driver_5.jpg" width="276" />
<img src="documents/Micro_RX_2ch_A1_Motor_Driver_6.jpg" width="416" />
#
### Function:
* MotorA = adjustable pwm/ch1
* MotorB = adjustable pwm/ch2
* Brake = on, off or adjustable effect 
* Normal mode = LED RX is lit
* Battery voltage 1S LiPo (4.2V) < monitored voltage = RX LED flash at a interval of 0.5s
* TX transmitter off or signal loss = RX LED flash at a interval of 0.1s 
* Fail-safe = MotorA and MotorB stopped

### Arduino pins:
* D9  - pwm1/MotorA
* D10 - pwm2/MotorA
* D3  - pwm3/MotorB
* D11 - pwm4/MotorB
#
* D2  - LED
* A7  - telemetry analog input RX battery
#
nRF24L01:
* A0  - CE
* A1  - CSN
* A2  - SCK
* A3  - MOSI
* A4  - MISO

### Used libraries:
* <RF24.h>                      https://github.com/nRF24/RF24 v1.3.9 
* <DigitalIO.h>                 https://github.com/greiman/DigitalIO
* "PWMFrequency.h" used locally https://github.com/TheDIYGuy999/PWMFrequency

### Schema:
![schema](https://raw.githubusercontent.com/stanekTM/RX_nRF24L01_Telemetry_Motor_Driver_Servo/master/RX_OpenAVRc_Multi_2ch_A1_Motor_Driver/documents/Schema_Micro_RX_2ch_A1_Motor_Driver.PNG)

### Layout:
![layout](https://raw.githubusercontent.com/stanekTM/RX_nRF24L01_Telemetry_Motor_Driver_Servo/master/RX_OpenAVRc_Multi_2ch_A1_Motor_Driver/documents/Layout_Micro_RX_2ch_A1_Motor_Driver.PNG)
#
Jiri StanekTM
