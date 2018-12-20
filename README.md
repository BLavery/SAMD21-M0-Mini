# SAMD21-Mini (branded Wemos)
Notes on using the Chinese "SAMD21 M0-Mini" board.<img align="right" src="images/mini.png">

This board in the "nano" sizing has an Atmel/MicroChip SAMD21G18 MCU, and is advertised as "Arduino Zero" compatible.
In hardware, the user LED on D13/PA17 is not fitted, although the PCB design seems to have intended it. As supplied, the Arduino-SAMD bootloader in installed in flash.

There are still 3 LEDs fitted, a power Led and a TX and RX Led, which are toggled (in software) when TX or RX data is happening. The arduino bootloader includes driver code to do this winking. Whether your application similarly drives these 2 Leds, "depends...".
