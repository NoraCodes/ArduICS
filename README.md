ArduICS
=======
An Arduino-compatible industrial control system for long-term, low maintenance applications. ArduICS uses simple, easy to manage XPAND interfaces, using 595HC shift registers; just send bits along the wire using ShiftIn(), and your outputs will switch.

PLCs are very hard to program, and far more powerful than needed for most small businesses. For many applications, a slower and cheaper system would work fine; but such a thing doesn't really exist. Now it does. ArduICS is easy to program, and once it's set up, it can be left running for a very long time. Plus, if you solder headers into the motherboard instead of soldering the controller in directly, you can swap out programs in seconds, or replace a broken or "bricked" controller cheaply.

ArduICS is open source; please feel free to contribute your XPAND boards, or any other projects designed to interface with the ArduICS motherboard.

###Motherboard
Current motherboard version: **0.2d**
* 5 relay outputs
* 4 analog inputs
* Hardware I2C and SPI interfaces
* UART interface (hook up via UART-to-USB cable or by the controller's onboard UART-to-USB chip to easily debug and extract data)
* 2 digital logic I/O ports (SPI SS or any other 5V logic)
* Screw terminal and barrel jacks for power
* Dual regulated input voltage
* PWR and CTRL indication at a glance
* Support for output expansion via shift registers


###XPAND Boards
* XPAND General **v0.1a**: 8 digital outputs. Use this to send digital signals to pretty much any 5V TTL devices (or through a level shifter to 3.3V or 12V devices). Or, use it to produce SS signals for your vast array of SPI sensors and actuators.
* XPAND LED **v0.1a**: 8 indicator LEDs. Use this module to allow at-a-glance status monitoring.

###XPAND Interface
* Uses 3.5mm stereo plug
* Simple to implement: Sleeve common, ring data, tip clock.
* Based on 74HC595 shift registers; tons of documentation available