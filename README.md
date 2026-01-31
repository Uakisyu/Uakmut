# Uakmut
Use real hardware to perform a MITM (man-in-the-middle) attack on mouse.
  
## How does Uakmut implement MITM?
1. It receives all commands from a physical mouse via a USB interface. Simultaneously, another USB interface is used to obtain the user's requested movement commands.
2. These instructions are processed and coordinate calculations are performed using an MCU (CH32V307VCT6).  
3. The fake mouse commands are output to the third USB port via another MCU (CH32V307VCT6).
  
## Overall design
2x MCU - CH32V307VCT6 (144Mhz)  
7x LED - Firmware version, Mode status, Flashing mode, Mouse input, Mouse output, Commend input, Error code.  
3x Button - Switch flashing mode, Switch ON/OFF, Force restart Uakmut.  

## LED Color
**F** - Firmware verison LED: Customizable. But generally speaking: Red represents the development version, Blue represents the beta version, Green represents the official version, Purple represents the Uakisyu's private version.  
**M** - Mode Status LED: **Red** (OFF, outputs only raw mouse commands), **Green**(ON, transmit processed mouse commands).
**R** - Flashing Mode: **Red** (OFF), **Green** (ON).  
**I** - Mouse input: **Red** (Mouse not connected), **Green** (Mouse connected).  
**O** - Mouse output: **Red** (PC not connected), **Green** (PC connected).  
**C** - Command input: **Red** (No command input), **Green** (Command input received).  
**E** - Error code: **Green** (No error). Please see the source code for other colors.  

## Button
**R** - Switch flashing mode (Press twice in a row)  
**M** - Switch ON/OFF (Press twice in a row)  
**F** - Force restart Uakmut (Press twice in a row)  

## LICENSE
This project is licensed under the **AGPL v3** license.
