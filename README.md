ArduICS
=======
##Overview
###What is ArduICS?
An Arduino-compatible industrial control system for long-term, low maintenance applications. ArduICS uses simple, easy to manage XPAND interfaces, using 74HC595 shift registers; just send bits along the wire using ShiftIn(), and your outputs will switch. ArduICS uses all through-hole (THT) components; no difficult surface-mount soldering means you can assemble everything yourself and save money, and maintenance is as easy as looking up a schematic and popping in a replacement part.

###Why not use an existing solution?
PLCs are very hard to program, and far more powerful than needed for most small businesses. For many applications, a slower and cheaper system would work fine; but such a thing doesn't really exist. Now it does. ArduICS is easy to program, and once it's set up, it can be left running for a very long time. Plus, if you solder headers into the motherboard instead of soldering the controller in directly, you can swap out programs in seconds, or replace a broken or "bricked" controller cheaply.

###What are the design principles?
ArduICS has a few simple design principles. Anything you submit should adhere to these.
* Safe; keep HV away from logic (and humans!)
* Simple; try not to use convoluted control schemes or proprietary interfaces
* Self-contained; try to make each module work by itself, and put as much documentation as possible on the PCB's silkscreen.
* Serial; don't connect parallel interfaces towards the motherboard unless absolutely necessary. Convert to parallel as close to the end as possible (use 74HC595s or similar chips). This keeps the number of wires and lines of code down.
* Extensible; Make sure your modules fit in with the rest of the ecosystem, and expand the capabilities of the system as a whole, rather than limiting them. For example, try to always pass busses through rather than capping them, and if there are extra inputs or outputs available on your ICs, try to make them available.

###What are my rights?
ArduICS is open source, under the GPLv3. You can do anything with it (yes, anything, including sell it) except sue me or change how it is licensed, as long as you:
* say where you got it (i.e., link back here)
* include a copy of or link to the GPLv3
*  say how you changed it (if at all)

###How can I help?
Please feel free to contribute your XPAND boards, or any other projects designed to interface with the ArduICS motherboard.

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
* XPAND Relay **v0.1a**: 8 relay-based outputs. Control your HV devices simply and reliably, but slowly.

###I2C Expansion Boards
* None yet.

###SPI Expansion Boards
* None yet.

###XPAND Interface
* Uses 3.5mm stereo plug
* Simple to implement: Sleeve common, ring data, tip clock.
* Based on 74HC595 shift registers; tons of documentation available