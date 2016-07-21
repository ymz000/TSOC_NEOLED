# TSOC_NEOLED

**TSOC_NEOLED** is a Eight-Channel WS2812 driver exapnsion board **thingSoC Reference Design.** 

**thingSoC Reference Designs** are example thingSoC implementations that implement
various reference and testing circuits for demonstrating the use of the thingSoC libraries.
These reference designs can serve as starting templates for user designs.

**TSOC_NEOLED** uses a programmable system on chip (PSoC4) with an eight (8) channel driver
to drive up to 512 WS2812 Color LED's, arranged as 64x8 (eight strings).
The **TSOC_NEOLED** can provide several different intefaces in order to make
interfacing large numbers of LEDs easy. The default protocol is an I2C interface :

1) I2C Serial DMX-512, Memory Mapped (**TSOC_NEOLED** looks like a 2048 byte I2C SRAM)

Other Interface protocols (Firmware update using FTDI/USB-UART or JTAG) :

2) UART Serial DMX-512 (200K Baud, N, 8, 1) with four DMX universes.

3) SPI Serial DMX-512, Memory Mapped (**TSOC_NEOLED** looks like a 2048 byte SPI SRAM)


[![thingSoC TSOC_NEOLED](https://raw.githubusercontent.com/thingSoC/TSOC_NEOLED/master/TSOC_NEOLED/images/TSOC_NEOLED_top.png?raw=true)*TSOC_NEOLED*](https://github.com/thingSoC/TSOC_NEOLED)

---------------------------------------

## TSOC_NEOLED Application Pictures

Using the TSOC_NEOLED to drive eight(8) strings of color LEDs for lighting our tandem bike for PedalPolooza 2016

[![thingSoC TSOC_NEOLED](https://raw.githubusercontent.com/thingSoC/TSOC_NEOLED/master/TSOC_NEOLED/images/light_the_ride2.png?raw=true)*TSOC_NEOLED*](https://github.com/thingSoC/TSOC_NEOLED)

---------------------------------------

## TSOC_NEOLED Arduino Sketch Examples

Under the "examples" directory are several Arduino IDE examples for using the TSOC_NEOLED board with Arduino IDE.
Using the Arduino "Wire" library for I2C communications, it is simple to control the TSOC_NEOLED

```c
 // Turn one color of one LED On
 Wire.beginTransmission(TSOC_NEOLED_I2CADDRESS);  // Start the I2C transaction
 Wire.write(row);                                 // Send the high byte of 16 bit memory address
 Wire.write(column);                              // Send the low byte of 16 bit memory address
 Wire.write(TSOC_NEOLED_LED_ON);                  // Send a single data byte  (we could send more...)
 Wire.endTransmission();                          // End the I2C transaction
```

---------------------------------------

## TSOC_NEOLED Status <a name="TSOC_NEOLED_status"/>

**04/28/2016:** 
Revision 1.1 - Initial Layout with Eight(8) channel driver.

**06/27/2016:**
Revision 1.2 - Added extra power connections for higher current support.


---------------------------------------

## TSOC_NEOLED Documentation Index <a name="TSOC_NEOLED_documentation_index"/>

[TSOC_NEOLED Project](http://thingsoc.github.io/projects/TSOC_NEOLED.html)

[TSOC_NEOLED Hardware](https://github.com/thingSoC/TSOC_NEOLED/tree/master/TSOC_NEOLED/hardware)


---------------------------------------

## thingSoC Documentation Index <a name="thingSoC_documentation_index"/>

[thingSoC Organization Website](http://thingSoC.github.io)

[thingSoC FAQ - Frequently Asked Questions](http://thingsoc.github.io/support/faq.html)

---------------------------------------

[![thingSoC](http://thingsoc.github.io/img/projects/thingSoC/thingSoC_thumb.png?raw=true) 
*thingSoC*](http://thingsoc.github.io)
