# Setup RTC I2C module

- Connect the module as in [Schematic](/media/Schematic.png).
- Make sure `Enable I2C (RTC Module)` in [boot/config.txt](files/boot/config.txt)
- SSH Login your device
- Add `rtc-ds1307` to `/etc/modules`
```
echo 'rtc-ds1307' | sudo tee -a /etc/modules
```
- Reboot the system: `sudo reboot`
- Make sure that the module is working: `sudo i2cdetect -y 1`.
- You should see a configured device on address `68:
```
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:                         -- -- -- -- -- -- -- --
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
20: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
30: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
40: -- -- -- -- -- -- -- -- -- -- -- -- UU -- -- --
50: -- -- -- -- -- -- -- 57 -- -- -- -- -- -- -- --
60: -- -- -- -- -- -- -- -- UU -- -- -- -- -- -- --
70: -- -- -- -- -- -- -- --
```
- Test hardware clock: `sudo hwclock --verbose`

```
hwclock from util-linux 2.36.1
System Time: 1690388057.571779
Trying to open: /dev/rtc0
Using the rtc interface to the clock.
Assuming hardware clock is kept in UTC time.
Waiting for clock tick...
ioctl(4, RTC_UIE_ON, 0): Invalid argument
Waiting in loop for time from /dev/rtc0 to change
...got clock tick
Time read from Hardware Clock: 2023/07/26 16:14:18
Hw clock time : 2023/07/26 16:14:18 = 1690388058 seconds since 1969
Time since last adjustment is 1690388058 seconds
Calculated Hardware Clock drift is 0.000000 seconds
2023-07-26 19:14:17.662126+03:00
```

![Schematic](/media/Schematic.png)

## References
- https://www.raspberrypi-spy.co.uk/2015/05/adding-a-ds3231-real-time-clock-to-the-raspberry-pi/