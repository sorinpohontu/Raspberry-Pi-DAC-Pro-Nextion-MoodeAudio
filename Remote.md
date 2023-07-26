# Connect and setup Remote

I was inspired by this: [https://moodeaudio.org/forum/showthread.php?tid=3584].

I'm using a IR sensor TSOP34836 [https://www.tme.eu/ro/details/tsop34836/module-receptoare-ir/vishay/] with a (clone) Apple Remote [https://www.aliexpress.com/item/4000517006403.html].

Basically, you can use any IR sensor with any Remote, see `Notes` below.

- See [TSOP34836 datasheet](docs/Datasheet/TSOP348.pdf) for details about pins.
- Connect pin 1 to `GPIO 17` (you will use `pin 11` for `CLI.py`)
- Copy [IR Remote Script](files/usr/local/sbin/ir-remote-moode.py) to: `/usr/local/sbin/ir-remote-moode.py`
- Create a `systemd` Service:

```
sudo nano /lib/systemd/system/ir_remote_moode.service
```

```
[Unit]
Description=IR Remote Moode Control

[Service]
Type=simple
ExecStart=/usr/bin/python /usr/local/sbin/ir-remote-moode.py

[Install]
WantedBy=multi-user.target
```

```
sudo systemctl enable ir_remote_moode
sudo systemctl start ir_remote_moode
```

![Schematic](/media/Schematic.png)

## Notes
Optionally, you can run `CLI.py` to learn and view your remote configuration.

```
pip3 install colorama
wget https://github.com/Lime-Parallelogram/pyIR/raw/master/pyIR.py
wget https://github.com/Lime-Parallelogram/pyIR/raw/master/CLI.py
python CLI.py
```

## References
- https://moodeaudio.org/forum/showthread.php?tid=3584
- https://gist.github.com/prasanthj/c15a5298eb682bde34961c322c95378b
- https://github.com/svirant/apple_ir_control
- https://github.com/Larvitar/MoodeIrRemote


