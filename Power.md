# Connect and setup Power ON/OFF button

I was inspired by this comment: [https://raspberrypi.stackexchange.com/a/85316].

I'm using [an I2C RTC module](RTC.md), so I want to use `GPIO 3` as `I2C Clock` and `wake from halt` [https://raspberrypi.stackexchange.com/q/22524].

- Connect a momentary switch for `Power ON / OFF`, as in [Schematic](/media/Schematic.png).
- Connect one pin to any free `Ground` (eg: 39)
- Connect the second pin to:
1. `GPIO 27` (you can use other unused pin, see [boot/config.txt](files/boot/config.txt))
2. Through diode to `GPIO 3 (I2C Clock)`. See the links above for `why` and details.

![Schematic](/media/Schematic.png)

## References
- https://raspberrypi.stackexchange.com/a/85316
- https://raspberrypi.stackexchange.com/q/22524
- https://elinux.org/RPI_safe_mode#cite_note-1
- https://forums.raspberrypi.com/viewtopic.php?t=318122
- https://gist.github.com/lbussy/9e81cbcc617952f1250e353bd42e7775

