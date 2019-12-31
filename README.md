xe-dongle-usb-bootloader
========================

This bootloader is a modified CDC bootloader from LUFA using the avr109 protocol.

Bootloader flashing:
--------------------

Example command to flash with the FTDI [TUMPA](https://www.diygadget.com/jtag-cables-and-microcontroller-programmers/tiao-usb-multi-protocol-adapter-jtag-spi-i2c-serial) device:

$ `avrdude -c tumpa -p m16u2 -v -e -u -U flash:w:BootloaderCDC.hex -U lfuse:w:0xDE:m -U hfuse:w:0xD9:m -U efuse:w:0xF4:m -U lock:w:0xCF:m`
