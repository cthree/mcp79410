# RTCC - MCP79410 Breakout Board

A small breakout board for the MCP79410 I2C RTCC/EEPROM and UID chip from Microchip.

![MCP79410](https://644db4de3505c40a0444-327723bce298e3ff5813fb42baeefbaa.ssl.cf1.rackcdn.com/aecf26e62adc8ed7e62a96d918672d97.png) ![Bottom](https://644db4de3505c40a0444-327723bce298e3ff5813fb42baeefbaa.ssl.cf1.rackcdn.com/65a8e8134772b609e3b54966704671fd.png)

You can [order this board](https://oshpark.com/shared_projects/WmGSs4wK) ready made
from oshpark.com. It's 1" x 1" so it will cost $5 for 3.

I use these to prototype new projects needing an RTCC. Feel free to do the same.
I designed this to be easy to hand solder. The battery holder and battery are
optional, you can use the VBAT pin as an alternate. VBAT can be used as a
battery level fuel gauge sense line if you connect it to an ADC.

R2 and R3 are 2K2 I2C pullup resistors which you may not need if you've got
pullups configured on your microcontroller ports or if you have them on your
bus already. Consider them optional.

The passives are all 0603 ERJ-3GEYJxxx Panasonic resistors and GRM188xxxxxx
capacitors from muRata. See the BOM for a complete parts list. Everything is
available from Digikey, this [saved cart](http://www.digikey.ca/short/3wd48v)
has everything you'll need.

Total cost for 3 PCBs and the parts to build them out works out to about $14.

When mounting and handling the module be aware that the battery holder is at +3V.
Don't accidentally short it to ground or you can expect undesired results. The
mounting holes close to the pins are unplated to avoid accidentally shorting to
ground with a screw head. Take care and maybe put some electrical tape over the
battery holder just in case.

## About the MCP794XX Realtime Clock/Calendar

The [Datasheet](http://ww1.microchip.com/downloads/en/DeviceDoc/20002266H.pdf)
is your primary reference. In addition there are a few
[Application Notes](http://www.microchip.com/wwwproducts/en/mcp79410)

The MCP7941x is a mid-range real-time clocks with advanced timekeeping features
such as the Power-Fail Timestamp, which can be used to log the time and duration
of power failures. With onboard digital trimming, these devices can provide
accurate timekeeping over a wide temperature range.

* 400 KHz I2C bus
* Battery Switchover (VBAT)
* Power-Fail Timestamp
* Digital trimming = +/- 127 PPM
* Compensates up to ~11 sec/day
* SRAM = 64 bytes
* EEPROM = 1K or 0K bits
* Unique ID = 64 bits

The 79410, 79411 and 79412 are all compatible with this breakout. The difference
between them is what is stored in the the 64 bit UID at the factory:

* MCP79410: Blank
* MCP79411: EUI-48
* MCP79412: EUI-64

Check the datasheet for details. The MCP79410 spec'ed for this breakout has
1Kbits of EEPROM and a blank UID.

## Software

### Linux

The MCP7941X is compatible with the DS-1307 RTCC. It is located at I2C address
0x6e. You'll want to use the rtc-ds1307 kernel driver available from kernel v3.19
on.

### Arduino/AVR

[Arduino MCP79412 RTC Library v1.0](https://github.com/JChristensen/MCP79412RTC)

###PIC

[AN1355](http://www.microchip.com//wwwAppNotes/AppNotes.aspx?appnote=en551346)
[AN1355 Code](http://ww1.microchip.com/downloads/en/DeviceDoc/RTCC_I2C_MCSET_FJ11_B06.zip)

### MSP430

[Driver](https://github.com/sbobovyc/MSP430/blob/master/I2C_test/RTCC_Driver.c)

## Bugs, Issues and Contributions

If you discover any issues with it or the parts used please let me know by opening
an issue or forking the repo and submitting a pull request with your fix.

Happy hacking!
