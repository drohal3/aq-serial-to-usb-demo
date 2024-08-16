# Example scripts for USB to serial converter / Raspberry Pi UART communication 
## Setup:
**Hardware:**
- Adafruit CP2102N Friend - USB to Serial Converter ([link](https://www.adafruit.com/product/5335))
- Raspberry Pi 4 or Raspberry Pi 5

**Wiring:**

| Converter | Raspberry Pi      | Note                                             |
|-----------|-------------------|--------------------------------------------------|
| GND       | 4 (GND)           |                                                  |
| CTS       |                   | not connected                                    |
| 5V        | 6 (5V)            |                                                  |
| TXD       | 10 (GPIO15 - RXD) | TXD and RXD might be swapped in some components  |
| RXD       | 8 (GPIO14 - TXD)  | TXD and RXD might be swapped in some components  |
| RTS       |                   | not connected                                    |

The USB output from the Converter is connected to a free USB port of the Receiver 
(can be the same as transmitter for demonstrating purposes).

> **Note:** PORT constants in the scripts must be adjusted. Typically, in transmitter, port is `"/dev/ttyS0"` 
> and in transmitter it is `"/dev/ttyUSB0"`.

**Scripts:** <br/>
The Python scripts located in this repository (each in its own directory) are intended to be run in 
a Raspberry Pi 4 or 5 device with Raspberrian OS and Python installed. Also, pyserial package is required.

## Transmitter
```bash
python3 ./transmitter/main.py
```

## Receiver
```bash
python3 ./receiver/main.py
```

## Common problems
- incorrect serial port - Adjust PORT constant in a script, discover ports with `ls -la /dev/tty*`
- swapped TXD and RXD cables