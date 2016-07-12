# Seeeduino Lite

## Introduction
Seeeduino Lite is a microcontroller based on ATmega32U4. Just like Arduino Leonardo, it saves a secondary processor needed for USB to serial communication. And this allows Seeeduino Lite appear to computer as a USB device, like keyboard and mouse. Derived from Leonardo, we also merged custom details of Seeeduino series into Seeeduino Lite, like selectable operating voltage, onboard Grove connectors and so on. It has 20 digital I/Os (7 of which can output PWM),a micro USB connection, a power jack, an ICSP header, and a reset button. It contains everything needed to support the microcontroller; simply connect it to a computer with a USB cable or power it with a AC-to-DC adapter to get started.

**Model:**[ARD05253P](https://www.seeedstudio.com/item_detail.html?p_id=1487)

![](https://raw.githubusercontent.com/SeeedDocument/Grove_Vibration_Motor/master/image/300px-Gvib.jpg)


## Specifications

- Microcontroller: ATmega32u4
- Operating Voltage: 5V
- Input Voltage (recommended): 7-12V
- Input Voltage (limits): 6-20V
- Digital I/O Pins: 20
- PWM Channels: 7
- Analog Input Channels: 12
- DC Current per I/O Pin: 40 mA
- DC Current for 3.3V Pin: 50 mA
- Flash Memory: 32 KB (ATmega32u4) of which 4 KB used by bootloader
- SRAM: 2.5 KB (ATmega32u4)
- EEPROM: 1 KB (ATmega32u4)
- Clock Speed: 16 MHz
  
## Interface

![](https://raw.githubusercontent.com/SeeedDocument/Grove_Vibration_Motor/master/image/700px-IMG_0506.jpg)

U1: 78M05 IC, Three-terminal positive voltage regulator.

U3: LD1117 IC, a Low Drop Voltage Regulator able to provide up to 800mA of Output Current.

U5: Atmega32U4 IC, 8-bit AVR Microcontroller with 32K Bytes of ISP Flash and USB Controller.


## Driver Installation
Download the driver files from here [https://github.com/Seeed-Studio/Signed_USB_Serial_Driver](https://github.com/Seeed-Studio/Signed_USB_Serial_Driver). 

Connect Seeeduino Lite to your computer via a micro-USB wire.

Wait for the new found hardware prompt.If the installer does not launch automatically, Navigate to the Windows Device Manager and find the Seeeduino Lite listing.

![](https://raw.githubusercontent.com/SeeedDocument/Grove_Vibration_Motor/master/image/700px-IMG_0506.jpg)

Right click and choose Update driver. When asked to install automatically or from a specific location, select "Browse my computer for driver software".

![](https://raw.githubusercontent.com/SeeedDocument/Grove_Vibration_Motor/master/image/700px-IMG_0506.jpg)

Choose "Search for the best driver in these locations", and check the box "incude this location in the search". Click the Browse button and navigate to drive you have downloaded. Select the drivers folder an click OK.


![](https://raw.githubusercontent.com/SeeedDocument/Grove_Vibration_Motor/master/image/700px-IMG_0506.jpg)

![](https://raw.githubusercontent.com/SeeedDocument/Grove_Vibration_Motor/master/image/700px-IMG_0506.jpg)

Replace two file in the path of Arduino. Open up Arduino-1.0.1/hardware/arduino/cores/arduino directory, replace the file:USBCore.cpp with the new USBCore.cpp.And replace file：boards.txt with the new boards.txt in the path:Arduino-1.0.1/hardware/arduino. Now, you can program and use the seeeduino lite as you use other Arduino boards.

## Resources
















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
- [Grove - Vibration Motor Eagle File](https://github.com/SeeedDocument/Grove_Vibration_Motor/blob/master/resource/Grove_-_Vibration_Motor_Eagle_Files.zip)
- [S9013datasheet](http://www.seeedstudio.com/wiki/images/9/9e/S9013.pdf)
- [ANDA-B1020_datasheet](http://www.seeedstudio.com/wiki/images/b/b7/ANDA-B1020_datasheet.pdf)
