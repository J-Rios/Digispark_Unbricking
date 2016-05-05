# Digispark_Unbricking

How to for unbrick digisparks that have fused incorrectly (reset disable) by burning micronucleus bootloader with a High Voltage Programmer.

-------------------------------------------------------------------------------------------------------------------------

Instructions:
  * Download the avrdude software (if you don't have it): http://www.nongnu.org/avrdude/
  * Download the micronucleus bootloader (if you don't have it): https://github.com/micronucleus/micronucleus
  * Set the bootloader file inside the avr-dude folder
  * Open a CMD session inside the avr-dude folder
  * Make the connections between the Digispark and the HV programmer
  * Type on CMD one of the following sentences (if you want pin PB5 reset enabled or disabled):
    - Reset enabled: avrdude -c usbasp -p t85 -U flash:w:t85_default.hex:i -U lfuse:w:0xF1:m -U hfuse:w:0xDF:m -U efuse:w:0xFE:m
    - Reset disabled: avrdude -c usbasp -p t85 -U flash:w:t85_default.hex:i -U lfuse:w:0xF1:m -U hfuse:w:0x5F:m -U efuse:w:0xFE:m

    - Note: usbasp (programmer), t85 (microcontroller), t85_default.hex (Bootloader file name)
