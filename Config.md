# Updating `/boot/config.txt`
- See [config.txt](files/boot/config.txt)
- Login by SSH to your device and make necessary changes: `sudo nano /boot/config.txt`

```
# Disable on-board audio
dtparam=audio=off
```

```
# Enable I2S DAC
dtparam=i2s=on
dtoverlay=iqaudio-dacplus
```

```
# Shutdown button on GPIO 27
dtoverlay=gpio-shutdown,gpio_pin=27
```

```
# IR Remote on GPIO 17
dtoverlay=gpio-ir,gpio_pin=17
```

```
# Enable serial ports
enable_uart=1
# Nextion Display on UART4 GPIO 8-11
dtoverlay=uart4
```
