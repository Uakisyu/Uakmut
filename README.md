# Uakmut
Use real hardware to perform a MITM (man-in-the-middle) attack on mouse.
  
## How does Uakmut implement MITM?
1. It receives all commands from a physical mouse via a USB interface. Simultaneously, another USB interface is used to obtain the user's requested movement commands.
2. These instructions are processed and coordinate calculations are performed using an MCU (CH32V307VCT6).  
3. The fake mouse commands are output to the third USB port via another MCU (CH32V307VCT6).
  
## Overall design
2x MCU - CH32V307VCT6 (144Mhz)  
6x LED - Firmware version, Mode status, flashing mode, Mouse input, Mouse output, Connection status with output command software.
2x Button - 

## LED Color
**F** - Firmware verison LED: Customizable. But generally speaking: Red represents the development version, Blue represents the beta version, Green represents the official version, Purple represents the Uakisyu's private version.  
**M** - Mode Status LED: **Red** (OFF, outputs only raw mouse commands), **Green**(ON, transmit processed mouse commands).

## LICENSE
This project is licensed under the **AGPL v3** license.
