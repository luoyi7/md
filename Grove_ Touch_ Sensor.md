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

   **Dillinger**

|AHLB|	TOG|	LPMB	|MOTB	|SLRFTB	|RST|	Q	|OPDO|
|:------|:-------|:-----|:------|:------|:------|:------|:------|
|Output Active High / Low|	Toggle mode|	Power Mode|	Max. On Time|	Sampling length|	RESET PIN	|CMOS Output|	Open Drain Mode|
|V|	V|	0|	1|	1	|X|	V|	X|
|Active| High|	Disabled|	LOW	|Infinite|	1.6 msec|	N/A|	Present|	N/A|

## Demonstration

**With Arduino**

![](https://raw.githubusercontent.com/SeeedDocument/Grove_Touch_Sensor/master/image/p.2.jpg)

This demo is going to show you how to turn on/off an LED.

**Demo Code:**
```sh
const int TouchPin=9;
const int ledPin=12;
void setup() {
pinMode(TouchPin, INPUT);
pinMode(ledPin,OUTPUT);
} 
 
void loop() {
int sensorValue = digitalRead(TouchPin);
if(sensorValue==1)
{
digitalWrite(ledPin,HIGH);
}
else
{
digitalWrite(ledPin,LOW);
}
}

```
**With** [Raspberry Pi](http://www.seeedstudio.com/wiki/GrovePi%2B)

1.You should have got a raspberry pi and a grovepi or grovepi+.

2.You should have completed configuring the development enviroment, otherwise follow [here ](http://www.seeedstudio.com/wiki/GrovePi%2B#Introducing_the_GrovePi.2B). 

3.Connection 
- Plug the sensor to grovepi socket D4 by using a grove cable.

4.Navigate to the demos' directory: 
```Javascript
  cd yourpath/GrovePi/Software/Python/
```
- To see the code
```Javascript
   nano grove_touch_sensor.py   # "Ctrl+x" to exit #
```
```Javascript
   import time
import grovepi

# Connect the Grove Touch Sensor to digital port D4
# SIG,NC,VCC,GND
touch_sensor = 4

grovepi.pinMode(touch_sensor,"INPUT")

while True:
    try:
        print grovepi.digitalRead(touch_sensor)
        time.sleep(.5)

    except IOError:
        print "Error"
```

5.Run the demo.
```Javascript
   sudo python grove_touch_sensor.py
```

## Resources
- [Eagle Files](https://github.com/SeeedDocument/Grove_Touch_Sensor/blob/master/resource/Touch_sensor_Eagle_File.zip)
- [TTP223pdf](http://garden.seeedstudio.com/images/d/d5/TTP223.pdf)
- [how to upload code](http://www.seeedstudio.com/wiki/Upload_Code)
