# Grove - Touch Sensor

## Introduction
Grove - Touch Sensor enables you to replace press with touch. It can detect the change in capacitance when a finger is near by. That means no matter your finger directly touches the pad or just stays close to the pad, Grove - Touch Sensor would outputs HIGH also.

## Specifications
Operating Voltage: 2.0 - 5.5V

Operating Current(Vcc=3V):1.5 - 3.0μA

Operating Current(VDD=3V):3.5 - 7.0μA

Output Response Time: 60 - 220mS

Used Chipset: TTP223-BA6


   **Dillinger**

|AHLB|	TOG|	LPMB	|MOTB	|SLRFTB	|RST|	Q	|OPDO|
|:------|:-------|:-----|:------|:------|:------|:------|:------|
|Output Active High / Low|	Toggle mode|	Power Mode|	Max. On Time|	Sampling length|	RESET PIN	|CMOS Output|	Open Drain Mode|
|V|	V|	0|	1|	1	|X|	V|	X|
|Active| High|	Disabled|	LOW	|Infinite|	1.6 msec|	N/A|	Present|	N/A|

## Demonstration

**With Arduino**

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
**With**[Raspberry Pi](http://www.seeedstudio.com/wiki/GrovePi%2B)
1.You should have got a raspberry pi and a grovepi or grovepi+.

2.You should have completed configuring the development enviroment, otherwise follow [here ](http://www.seeedstudio.com/wiki/GrovePi%2B#Introducing_the_GrovePi.2B). 

3.Connection 
