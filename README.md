<span style="font-size: 50px;"><p align="center">🖱 __Uakmut__ 🕹</p></span>
=
<p align="center"><a href="https://github.com/Uakisyu/Uakmut/blob/main/README_CN.md">中文文档</a></p>
<p align="center">🏮 Released during the 2026 Lunar New Year - Happy Lunar New Year! 🏮</p>

# Uakmut
Use real hardware to perform a MITM (man-in-the-middle) attack on mouse.
  
## How does Uakmut implement MITM?
1. It receives all commands from a physical mouse via a USB interface. Simultaneously, another USB interface is used to obtain the user's requested movement commands.
2. These instructions are processed and coordinate calculations are performed using an MCU (CH32V307VCT6).  
3. The fake mouse commands are output to the third USB port via another MCU (CH32V307VCT6).

## Design Goals
Uses a high-speed USB 2.0 interface to achieve stable mouse polling rates of ***125Hz ~ 8KHz***.

## Overall design
2x MCU - CH32V307VCT6 (144Mhz)  
7x LED - Firmware version, Mode status, Flashing mode, Mouse input, Mouse output, Commend input, Error code.  
3x Button - Switch flashing mode, Switch ON/OFF, Force restart Uakmut.  
1x USB 2.0 FS (Fast Speed, 12Mbps)  
2x USB 2.0 HS (High Speed, 480Mbps)  

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

## PCB?
The PCB design will not be made public because this project was created for my own use, the source code is for reference only, and I will not release any compiled firmware.  
Currently, I have no intention of selling the PCB design, but commercial collaborations are possible...  
If you really need it, you can contact me on Telegram: @Uakisyu  

## Uakmut version Notes
**[Developing]** Uakmut v1 is the first release version, implementing all features.  
**[Unreleased]** Uakmut v2 is an optimized version, aiming to reduce costs and replace the MCU with a lower-cost MCU. The source code will be modified to adapt to the new MCU.  
Of course, the latest changes will be pushed to the main branch.  

## LICENSE
This project is licensed under the **AGPL v3** license.
