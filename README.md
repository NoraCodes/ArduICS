ArduICS
=======
## Overview
### Vital Statistics

* Controller: **Atmel ATMega 32u4** on 5V at 16MHz
* Bus Support: **XPAND** **I2C** **SPI** **UART** **USB**
* Programmable via **USB** in **Wiring** or **AVR-C**
* Inputs/Outputs: **5x 5V Digital** and **4x 10-bit analog** and **3x relay** (contact rated 120 VAC / 30 VDC @ 1 A)

### What is ArduICS?
An Arduino-compatible industrial control system for long-term, low maintenance applications. ArduICS uses simple, easy to manage XPAND interfaces, using 74HC595 shift registers; just send bits along the wire using ShiftIn(), and your outputs will switch. ArduICS uses mostly through-hole (THT) components; no difficult surface-mount soldering means you can assemble everything yourself and save money, and maintenance is as easy as looking up a schematic and popping in a replacement part.

### What is ArduICS XPAND?
XPAND is a very simple "bus" based on 74HC595 SIPO (serial in parallel out) shift registers. Using only two digital I/O pins, huge numbers of devices can be controlled (hundreds of relays, LEDs, or anything else that can be controlled with a digital signal). It is comparatively slow, so SPI, I2C, or a dedicated digital I/O pin are still recommended for complex/fast/PWM signals, but XPAND is an extremely simple way to control a lot of whatever you need to control. It uses standard 3.5 mm stereo cable, which is already resistant to electrical noise and easy to route.

### Why not use an existing solution?
PLCs are very hard to program, and far more powerful than needed for most small businesses. For many applications, a slower and cheaper system would work fine; but such a thing doesn't really exist. ArduICS is easy to program (using either the Arduino's Wiring language or AVR-C), and once it's set up, it can be left running for a very long time. Plus, if you solder headers into the motherboard instead of soldering the controller in directly, you can swap out programs in seconds, or replace a broken or "bricked" controller cheaply. Its "brain" is the ATMega32u4 on [LadyAda's breakout board](http://www.adafruit.com/products/296?&main_page=product_info&cPath=19&products_id=296)

## Hardware

### Motherboard
Current motherboard version: **Mk2**
<img src="https://raw.githubusercontent.com/SilverWingedSeraph/ArduICS/master/images/AICS%20Motherboard%20Mk2_pcb.jpg">

#### Board:

* 3x relay output ports
* 4x analog I/O ports @ 20 mA
* 5x 5V TTL digital I/O ports @ 20mA
* 1x each:
	* Hardware accelerated **I2C** 
	* Hardware accelerated **SPI** 
	* Hardware accelerated **UART**
	* Native **USB 2.0**
	* Software **XPAND**
* 4 amp 5 volt supply on board (for powering peripherals)
* Dual regulated input voltage
* Power and Controller indication at a glance
* Supports resetting controller from external button or logical device
* Support for XPAND bus:
	* Uses 3.5mm stereo plug
	* Simple to implement: Sleeve common, ring data, tip clock.
	* Based on 74HC595 shift registers; tons of documentation available
	* Uses Arduino ShiftOut() function

#### Controller:

ATMega 32u4 by Atmel on LadyAda's beautiful breakout board

* 32K Non Volatile Memory
* 2.5K Volatile RAM
* 16 MHz Clock
* 5V TTL Logic Level
* Natively USB and ISP/ICSP Programmable

### XPAND Boards
* XPAND General **v0.1a**: 8 digital outputs. Use this to send digital signals to pretty much any 5V TTL devices (or through a level shifter to 3.3V or 12V devices). Or, use it to produce SS signals for your vast array of SPI sensors and actuators.
* XPAND LED **v0.1a**: 8 indicator LEDs. Use this module to allow at-a-glance status monitoring.
* XPAND Relay **v0.1a**: 8 relay-based outputs. Control your HV devices simply and reliably, but (relatively) slowly.

### I2C Expansion Boards
* 16 Pin I/O with MCP23017: Use this when there just aren't enough digital I/O pins. Can use up to 8 of these on one I2C bus.
* 1MB EEPROM: A tiny board with 1MB of non-volatile memory that can be accessed quickly over the I2C bus. Up to 8 on one I2C bus.

### SPI Expansion Boards
* SPI RTC: A battery-backup Real Time Clock. Keep fairly precise time even when your ICS system is off.

### Other Expansion Boards
* Power Regulator for Peripherals **v0.1a**: Provide clean, regulated power to your XPAND boards and other peripherals. Input +6 to +12 volts (from an ATX or other cheap power supply), and get out +5 volts of beautifully flat, clean voltage.

## Contributing and Meta

### What are the design principles?
ArduICS has a few simple design principles. Anything you submit should adhere to these.

* Safe; keep HV away from logic (and humans!)
* Simple; try not to use convoluted control schemes or proprietary interfaces
* Self-contained; try to make each module work by itself, and put as much documentation as possible on the PCB's silkscreen.
* Serial; don't connect parallel interfaces towards the motherboard unless absolutely necessary. Convert to parallel as close to the end as possible (use 74HC595s or similar chips). This keeps the number of wires (and lines of code!) low.
* Extensible; Make sure your modules fit in with the rest of the ecosystem, and expand the capabilities of the system as a whole, rather than limiting them. For example, try to always pass busses through rather than capping them, and if there are extra inputs or outputs available on your ICs, try to break them out, even if only to headers or unpopulated pads.

### What are my rights?
(Lawyers should see the `LICENSE` file.) ArduICS is open source, under the GPLv3. You can do anything with it (yes, anything, including sell it) except sue me or change how it is licensed, as long as you:
* say where you got it (i.e., link back here)
* include a copy of or link to the GPLv3
*  say how you changed it (if at all)

### How can I help?
Please feel free to contribute your XPAND boards, or any other projects designed to interface with the ArduICS motherboard. Everything is currently being designed in [Fritzing](http://fritzing.org/home/) and should be in Fritzing Zip (.fzz) format. This is the default save format. If you submit a module using a different format such as Gerber, please include the PCB files, BoM, and any pertinent documentation.

Have ideas for more modules but don't have the know-how to make them yourself? Notice problems with the existing boards, or ways improvements could be made? First, make sure nobody else has submitted the same thing; then [file an issue](https://github.com/SilverWingedSeraph/ArduICS/issues/new).

