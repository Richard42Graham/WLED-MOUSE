# WLED-Mouse

*Note: PCB is still very much work in progress*

PCB files for a for ESP32 board that can attach an INMP441 or ICS-43434 I²S microphone. It is intended to use together with [SR-WLED](https://github.com/atuline/WLED/) for mixing sound reactive and addressable LEDs together.

## I2S Digital Microphone information
The INMP441 is an omnidirectional digital microphone which communicates via I²S. It can be bought from a number of places, for example [Aliexpress](https://www.aliexpress.com/i/32962426410.html).


Hookup instructions are taken from the [SR-WLED wiki](https://github.com/atuline/WLED/wiki/Digital-Microphone-Hookup#i2s-digital-audio).
| from INMP441, ICS-43434 | to ESP32 GPIO | |
| ---   | ---   | --- |
| L/R   | Gnd   | ground => left channel. Don't leave this pin unconnected!
| SD    | 32    | serial data
| WS    | 15    | left right clock
| SCK   | 14    | serial clock
| --    | 0     | master clock (if needed)
| VDD   | 3.3V  | power don't use 5V!
| GND   | Gnd   | ground, 0V

Steps in WLED
1. Fetch the binary from [SR-WLED](https://github.com/atuline/WLED/releases/latest) and flash to ESP32 board
1. Boot up WLED device and go to the "Sound setting" menu
2. Select `Generic I2S`
3. Reboot device
4. Have fun with sound reactive LEDs
