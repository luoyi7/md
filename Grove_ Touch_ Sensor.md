# Grove - Vibration Motor

## Introduction
This is a mini vibration motor suitable as a non-audible indicator. When the input is HIGH, the motor will vibrate just like your cell phone on silent mode.

**Model:**[ ROB51043P](https://www.seeedstudio.com/item_detail.html?p_id=839)

![](https://raw.githubusercontent.com/SeeedDocument/Grove_Touch_Sensor/master/image/p1.jpg)

## Features
- Grove compatible
- Non-audible
- Low power consumption
- High reliability

## Specifications

|Item|	Min|	Typ|	Max|
|:------|:-------|:-----|:------|
|Operate Voltage|	3.0V|	5.0V	|5.5V|
|Control Mode|	Logic Level  (When Logic HIGH, the motor is ON. When LOW, the motor is OFF.)|
|Rated speed|	9000 rpm|
## Usage
  
**With Arduino**

To make it vibrate is just as easy as to turn on an LED. Here is an example showing how to turn on the vibration motor.

1. Plug it onto the Digital port 9 of Grove - Base Shield using a Grove cable.
2. Plug the Grove - Base Shield onto Arduino.

![](https://raw.githubusercontent.com/SeeedDocument/Grove_Touch_Sensor/master/image/p.2.jpg)


3.Connect Arduino to PC by using a USB cable.

4.Copy and paste code below to a new Arduino sketch, and upload it to your Arduino. Please click [ here](http://www.seeedstudio.com/wiki/GrovePi%2B) if you do not know how to upload.
Demo code like:
```sh
 
int MoPin = 9;    // vibrator Grove connected to digital pin 9

void setup()  { 
  pinMode( MoPin, OUTPUT );
} 

void loop()  { 

    digitalWrite(MoPin, HIGH);         
    delay(1000);       
                     
    digitalWrite(MoPin, LOW);         
    delay(1000); 
 }

}

```
Now, feel the vibration of your motor!

**With** [Raspberry Pi](http://www.seeedstudio.com/wiki/GrovePi%2B)

1.You should have got a raspberry pi and a grovepi or grovepi+.

2.You should have completed configuring the development enviroment, otherwise follow [here ](http://www.seeedstudio.com/wiki/Upload_Code). 

3.Connection 
- Plug the sensor to grovepi socket D4 by using a grove cable.

4.Navigate to the demos' directory: 
```Javascript
  cd yourpath/GrovePi/Software/Python/
```
- To see the code
```Javascript
    nano grove_vibration_motor.py   # "Ctrl+x" to exit #
```
```Javascript
   import time
import grovepi

# Connect the Grove Vibration Motor to digital port D8
# SIG,NC,VCC,GND
vibration_motor = 8

grovepi.pinMode(vibration_motor,"OUTPUT")

while True:
    try:
        # Start vibrating for 1 second
        grovepi.digitalWrite(vibration_motor,1)
        print 'start'
        time.sleep(1)

        # Stop vibrating for 1 second, then repeat
        grovepi.digitalWrite(vibration_motor,0)
        print 'stop'
        time.sleep(1)

    except KeyboardInterrupt:
        grovepi.digitalWrite(vibration_motor,0)
        break
    except IOError:
        print "Error"
```

5.Run the demo.
```Javascript
   sudo python grove_vibration_motor.py
```
## Version Tracker

|Revision|	Descriptions|	Release|
|:------|:----------------|:------------|
|v0.9b|	     Initial public release   |	May 10, 2011  |
|v1.0	|    directly use a I/O port to drive vibration Motor   	|Nov 5, 2011|
|v1.2|   	add a transistor, use bigger current to drive Vibration Motor   |	July 11, 2013|

## Resources
- [Eagle Files](https://github.com/SeeedDocument/Grove_Touch_Sensor/blob/master/resource/Touch_sensor_Eagle_File.zip)
- [TTP223pdf](http://garden.seeedstudio.com/images/d/d5/TTP223.pdf)
- [how to upload code](http://www.seeedstudio.com/wiki/Upload_Code)
