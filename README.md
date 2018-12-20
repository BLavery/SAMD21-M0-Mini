# SAMD21 M0-Mini (branded Wemos)
Notes on using the Chinese "SAMD21 M0-Mini" board.<img align="right" src="images/mini.png">

## Hardware:

This board in the "nano" sizing has an Atmel/MicroChip SAMD21G18 MCU, and is advertised as "Arduino Zero" compatible.
In hardware, the user LED on D13/PA17 is not fitted, although the PCB design seems to have intended it. A schematic image is attached above, amended to be as accurate as I believe. 

There are still 3 LEDs fitted, a power Led and a TX and RX Led. The Rx and Tx ones are toggled (__in software__) when TX or RX data is happening. The arduino bootloader includes driver code to do this winking. Whether your application similarly drives these 2 Leds, "depends...".

The obvious application types available are 
 - arduino sketch
 - circuitpython
 - manually set up toolchain with compiler & uploader

This set of notes looks at the first two of these. If you are doing your own suite, you are smart enough to not need these notes!

## Bootloader:

From the factory, the MCU chip's ROM-based bootloader seems to support writing to flash only by ICE/SWD/Jlink. For hobby or low level use, flashing every sketch or program solely that way is in the "too much trouble" basket. Therefore a flash-based secondary bootloader is usually installed once, and left alone thereafter. The flash-based bootloader should offer easier ways to reflash your software.

On the board as supplied, a bootloader in installed in flash. It's an "arduino-zero compatible", so the arduino bootloader is included. This allows programming your sketch by DFU on the USB port, and the Arduino IDE has drivers for that built in.

But there is an alternative Adafruit bootloader more cleanly matched to Adafruit's circuitPython. So far I have resisted changing the bootloader, as circuitPython can be managed while leaving the arduino one there. 

More info?
 - https://github.com/arduino/ArduinoCore-samd/tree/master/bootloaders/zero
 - 

