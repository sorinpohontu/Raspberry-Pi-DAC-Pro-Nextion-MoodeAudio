# Power ON/OFF button

I was inspired by this comment: [https://raspberrypi.stackexchange.com/questions/72676/can-you-make-an-on-off-power-button-with-a-single-non-i2c-gpio-pin/85316#85316].

I'm using [an I2C RTC module](RTC.md), so I want to use `GPIO 3` as `I2C Clock` and `wake from halt` [https://raspberrypi.stackexchange.com/questions/22524/power-on-from-idle-with-gpio3-undocumented].

- Use a momentary switch for `Power` button
- Connect one pin to any free `Ground` (eg: 39)
- Connect the second pin to:
1. `GPIO 27` (you can use other unused pin, see [boot/config.txt](files/boot/config.txt))
2. Through diode to `GPIO 3 (I2C Clock)`. See the links above for details.

![Schematic](/media/Schematic.png)

## References
- https://raspberrypi.stackexchange.com/questions/72676/can-you-make-an-on-off-power-button-with-a-single-non-i2c-gpio-pin/85316#85316
- https://raspberrypi.stackexchange.com/questions/22524/power-on-from-idle-with-gpio3-undocumented
- https://elinux.org/RPI_safe_mode#cite_note-1
- https://forums.raspberrypi.com/viewtopic.php?t=318122

