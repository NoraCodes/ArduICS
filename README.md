ArduICS
=======
An Arduino-compatible industrial control system for long-term, low maintenance applications. ArduICS uses simple, easy to manage XPAND interfaces, using 595HC shift registers; just send bits along the wire using ShiftIn(), and your outputs will switch.

PLCs are very hard to program, and far more powerful than needed for most small businesses. For many applications, a slower and cheaper system would work fine; but such a thing doesn't really exist. Now it does. ArduICS is easy to program, and once it's set up, it can be left running for a very long time.

ArduICS is open source; please feel free to contribute your XPAND boards, or an other projects designed to interface with the ArduICS motherboard.

###Motherboard
Current motherboard version: **0.1d**
* 5 relay outputs
* 5 analog inputs
* SPI interface
* UART interface
* 2 digital I/O ports
* Screw terminal and barrel jacks for power
* Dual regulated input voltage
* PWR and CTRL indication at a glance
* Support for output expansion via shift registers

###XPAND Boards
* XPAND General **v0.1a**: 8 digital outputs
* XPAND LED **v0.1a**: 8 indicator LEDs

###XPAND Interface
* Uses 3.5mm stereo plug
* Based on 595HC shift registers