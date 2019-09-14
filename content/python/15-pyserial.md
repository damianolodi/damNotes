---
title: "PySerial"
draft: false
arguments: [""]
weight: 15
---

([Docs](https://pyserial.readthedocs.io/en/latest/shortintro.html))

```py
import serial

ser = serial.Serial(port = '/dev/tty.SLAB_USBtoUART',
                    baudrate = 9600,
                    bytesize = serial.EIGHTBITS,
                    parity = serial.PARITY_NONE,
                    stopbits = serial.STOPBITS_ONE,
					timeout = 3 #s
                    )
```

-   `python -m serial.tools.list_ports` &rarr; prints a list of available ports.
