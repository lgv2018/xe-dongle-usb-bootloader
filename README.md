xe-dongle-usb-bootloader
========================

This bootloader is a slightly modified CDC bootloader from LUFA using the avr109
protocol.


Recommended fuse values
-----------------------

| Fuse group | Value | Avrdude command   |
|------------|-------|-------------------|
| LOW        | 0xDE  | -U lfuse:w:0xDE:m |
| HIGH       | 0xD9  | -U hfuse:w:0xD9:m |
| EXTENDED   | 0xF4  | -U efuse:w:0xF4:m |


Bootloader flashing:
--------------------

Example command to flash with the FTDI [TUMPA](https://www.diygadget.com/jtag-cables-and-microcontroller-programmers/tiao-usb-multi-protocol-adapter-jtag-spi-i2c-serial) device:

$ `avrdude -c tumpa -p m16u2 -v -e -u -U flash:w:BootloaderCDC.hex -U lfuse:w:0xDE:m -U hfuse:w:0xD9:m -U efuse:w:0xF4:m`
