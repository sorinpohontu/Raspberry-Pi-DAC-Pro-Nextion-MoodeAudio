# Raspberry Pi DAC Pro with Nextion display running MoodeAudio 8

# Hardware
- Raspberry Pi 2 Model B Rev 1.1 [https://en.wikipedia.org/wiki/Raspberry_Pi]
- Raspberry Pi DAC Pro (former IQaudIO DAC Pro) [https://www.raspberrypi.com/products/dac-pro/]
- Nextion Display
- RTC
- Apple IR Remote

# Documentation
See [docs](docs).
# Drawings
See [drawings](drawings).

# Initial setup
- Use Raspberry Pi Imager [https://www.raspberrypi.com/software] to install moodeAudio Legacy[^1] [https://moodeaudio.org/] to SD Card.
- Make sure you have selected `Enable SSH` on Raspberry Pi Imager (`Advanced options`)

## Setup
1. Update `/boot/config.txt` [Config.md](Config.md)
2. Update `Audio Settings` [Audio.md](Audio.md)
3. Connect and setup Power button [Power.md](Power.md)
4. Setup RTC I2C module [RTC.md](RTC.md)

---
[^1]: Raspberry Pi 2 Model B Rev 1.1 does not support 64-bit kernel.