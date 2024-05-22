# COV-CARE
(COVID CARE USING ARDUINO ROBOT)
TEAM NAME: TEAM SIGMA

OBJECTIVE:
 To supply prescribed medicines to covid patients in the isolated ward without any physical contacts between them and the disinfected people using Arduino microcontroller. 
                     

COMPONENTS USED:
Motor driver (L298N 2A), Arduino uno, Infrared, ultrasonic and colour sensors, motors, lithium-ion battery, servo motor etc.
MOTOR DRIVER:
  The L298N is a dual H-Bridge motor driver which allows speed and direction control of two DC motors at the same time. The module can drive DC motors that have voltages between 5 and 35V, with a peak current up to 2A.
  
ARDUINO UNO:
  Arduino UNO is a microcontroller board based on the ATmega328P. It has 14 digital input/output pins (of which 6 can be used as PWM outputs), 6 analog inputs, a 16 MHz ceramic resonator, a USB connection, a power jack, an ICSP header and a reset button. It contains everything needed to support the microcontroller; simply connect it to a computer with a USB cable or power it with a AC-to-DC adapter or battery to get started. You can tinker with your UNO without worrying too much about doing something wrong, worst case scenario you can replace the chip for a few dollars and start over again.  

IR SENSOR:
  FC-51 IR Sensor emits and detected infrared radiations. IR radiations are part of the electromagnetic spectrum, with wavelength higher than that of visible light, and are generally invisible to the human eye.
As per the property of light — light falling on a smooth shiny surface bounces off in a particular direction i.e. reflection — the ray send by IR Transmitter gets reflected from a surface and falls on IR Receiver. Subsequently, the receiver’s resistance drops, and a LOW/0 signal is sent by the OUT pin to the microcontroller.
Similarly, when the light sent isn’t reflected either because there is no surface ahead or the surface ahead absorbs light, the resistance of the receiver rises and a HIGH/1 signal is sent by OUT pin to the microcontroller. 

ULTRASONIC SENSOR:
  Ultrasonic Sensor HC-SR04 is a sensor that can measure distance. It emits an ultrasound at 40 000 Hz (40kHz) which travels through the air and if there is an object or obstacle on its path It will bounce back to the module. Considering the travel time and the speed of the sound you can calculate the distance.
The configuration pin of HC-SR04 is VCC (1), TRIG (2), ECHO (3), and GND (4). The supply voltage of VCC is +5V and you can attach TRIG and ECHO pin to any Digital I/O in your Arduino Board.

COLOUR SENSOR:
  The module has an 8×8 photodiode array, 16 of them with Red filter, 16 with blue one, 16 with green one and 16 without a filter (clear), we select what filter to use and read its value, and in the code we combine them depending on the applciation or project.
The light is detected by the photodiodes and the output is a frequency proportional to the current flowing through the photodiodes which is related to the filter used and the object’s color detected.
The module has (Vcc/GND) pins, they are redundant.
– S0/S1 pins control the output frequency scalling
– S2/S3 pins control which set of photodiodes we gonna measure (Red/Green/Blue/Clear)
– Out is the output signal and LED pin controls the LEDs on the front.

This option permits the module to be used with different measuring techniques, and types of microcontrollers, in the tutorial and codes I kept using it at 100%, you can change it if you want it depends just on the logic level of their pins (HIGH/LOW). Photodiodes set selection By also controlling the logic levels of S2/S3 we can select which filter or no filter to use, in the code I go through Red/Green/Blue, if your application require one or two filters only you can do it too.For the LED pin, if it’s not connected, the LEDs will light up automatically, but if you want to turn them off you can put the LED pin to LOW, (it depends on your application and condition).For the Out pin, as the signal given by the sensor is a frequency,   we measure the duration as they are related (Duration=1/Frequency), so the higher the frequency of a color, the lower is the duration measured, which means that the object detected has that color (check the tutorial).

SERVO MOTOR:
  The Servo Library is a great library for controlling servo motors. In this article, you will find two easy examples that can be used by any Arduino board.
The first example controls the position of a RC (hobby) servo motor with your Arduino and a potentiometer. The second example sweeps the shaft of a RC servo motor back and forth across 180 degrees.
 
WORKING:
The Arduino uno helps to control all the elements in which the IR sensor detects the black line and gives the output to the Arduino uno. With the  output from IR the Arduino uno gives information to the motor drive to go in a correct path. With IR sensor we cannot detect any obstacle and colour so Ultrasonic and colour sensor are used. First Ultrasonic sensor detects the obstacle in the determined distance .If there is no obstacle the  device moves in the correct direction .In other case the ultrasonic will give data to Arduino uno that there is a obstacle .Then the Arduino uno will direct the motor driver in the way to avoid obstacle.After that the device is again comes to the black line.Here the colour sensor detects the red colour.If red colour is detected by colour sensor the Arduino uno stops the device in order to take the medicine by the patient .The red colour is placed near to the patient bed.
The follow of program process is:
Case 1:
                Ultrasonic —->Arduino uno(no obstacle) –->colour sensor—>Arduino uno(no red colour)—>IR sensor —>Arduino uno(black line detection) —>motor drive(goes on)
Case 2:
          Ultrasonic —->Arduino uno(no obstacle) –->colour sensor—>Arduino uno(red colour)—>motor drive(stop) →IR sensor —>Arduino uno(black line detection) —>motor drive


ADVANTAGES:
    BASED ON USAGE OF COMPONENTS:
		There are many advantages based on the usage of components. For example instead of a line following sensor we used only two IR sensors which did the same work as the line following sensor.
CONCLUSION:
 Using this robot and applying a black tape through cover every patient’s bed we can circulate the medicines through the robot. At the stops we can use red tape to stop for few minute with a beep sound to notify the patient and collect their medicines without and can easily sanitize the robot without any physical contact with the care takers.
         

















MENTOR: M. VIGNESH
TEAM MEMBERS: 
1.	S.R. ABHINESH
2.	S. MADHESHWARAN
3.	B. NANDHAN
4.	R. GIRINITH


