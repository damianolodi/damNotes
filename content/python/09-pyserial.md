---
title: "PySerial"
draft: false
---

[Documentation](https://pyserial.readthedocs.io/en/latest/shortintro.html)

```py
import serial
```

-   `python -m serial.tools.list_ports` prints a list of available ports.

* * *

## Port Opening

```py
ser = serial.Serial(	port='/dev/tty.SLAB_USBtoUART',
                    	baudrate=9600,
                    	bytesize=serial.EIGHTBITS,
                    	parity=serial.PARITY_NONE,
                    	stopbits=serial.STOPBITS_ONE,
					   	timeout=3 #s
                    )
```

-   `Serial` open the port and create an object.
    		\* `timeout` set the time after which the reading process is stopped (in seconds)
-   

* * *

\#code/python/modules
