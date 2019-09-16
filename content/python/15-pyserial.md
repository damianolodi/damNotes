---
title: PySerial
draft: false
arguments:
  - ''
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

- `python -m serial.tools.list_ports` &rarr; prints a list of available ports

- `ser.reset_input_buffer()` &rarr; flush input buffer (discard all the content)

- `ser.readinto(bytearray)` &rarr; **read up to *len(bytearray)* characters** and store them into _bytearray_. Return number of bytes red ([doc](https://pyserial.readthedocs.io/en/latest/pyserial_api.html#serial.Serial.readinto))

- `ser.close()` &rarr; close the serial connection

- `ser.open()` &rarr; open the serial connection. Automatically called when the _Serial_ object is created
