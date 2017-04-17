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

If you discover any issues with it or the parts used please let me know by opening
an issue or forking the repo and submitting a pull request with your fix.

Happy hacking!
