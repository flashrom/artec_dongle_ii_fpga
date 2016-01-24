# LPC ROM, SPI ROM, 8bit ROM emulator on Artec Dongle II board

Freed from http://opencores.org/project,artec_dongle_ii_fpga

Information below is from the project's website on opencores.org.

Original project maintainer:
 - Toomessoo, Jüri 
 - Raudsepp, Mart 

Name: artec_dongle_ii_fpga
Created: Nov 4, 2008  
Updated: Mar 5, 2012  
Category: Prototype board  
Language: Other  
Development status: Stable  
Additional info: none  
WishBone Compliant: No  
License: LGPL  

## Planned Features

- LPC ROM(RAM?) 
- Flash regions Memory read, Firmware hub read, (IO read and write) 
- PSRAM regions Memory read and write, Firmware hub read, (IO read and write) 
- SPI ROM 
- Flash regions read 
- PSRAM regions read 
- 8 bit ROM 
- read (with standard CS, OE, WE, DATA, ADDR interface on the 32 extension pins) 
- Post code trace 
- Boot trace (list all memory cycles possible at least on LPC) 
- Simple Logic Analyzer with 32 pins and 32 pin GPIO python module support 
- VHDL Firmware update trough USB data cable 

## Status 

### DONE 

- code transfer from Dongle I 
- PSRAM support added to memory interface and USB interface (4MB write time is 4 sec under Linux read is 10 sec) 
- New jumper block with LED indicators 
- dongle.py updated for initial features 
- dev_present signal switching from PC by default is low (has strong pull down 330 ohm for backward compatibility) 
- removed the need for reset after programming to free memory bus lock (lock is now controlled by the dongle.py software) 
- Added UART 16550 support over LPC with selectable base addresses 

### TODO 

- Write multi-clock domain scalable memory bus arbiter (firmware) 
- SPI boot support (firmware) 
- 8 bit parallel ROM support code (firmware) 
- write GPIO support (firmware) and supporting Python module (software) 
- boot trace feature (save all accessed addresses and data and send to PC) (firmware) 
- write new update.py to work trough FTDI D2xx bit bang feature (software) 
- write 16 bit to 8 bit FIFO bridge to further speed up USB transfer on PSRAM regions (firmware) 
- try to rewrite Uspp read() in linux implementation to support more than word read at a time from OS (software) 
- write EPROM support code (firmware) 
- write software jumper support with settings stored/restored from EPROM (firmware) 
- write or port Analyzer code (firmware) 

## Description 

Project to create generic emulator/debugger/analyzer with 
on-the-fly reprogrammable firmware on Artec Dongle II board (containing Altera Cyclone III, Flash 16MB, PSRAM 16MB (UltraCap for image retention), FTDI usb, 32 GPIO pins, 4 segment LED, 8 green LEDs, 1 green/red LED, 8 pins for LPC/SPI bus, 6 pin extension header, EPROM 1024 bytes).
