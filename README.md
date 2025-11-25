# INA219 Power Monitor

Minimal Python script to read bus voltage, current, power and an approximate battery percentage from an INA219 current/power monitor over I²C.

## Requirements

- Python 3
- `smbus`
- I²C enabled on the host (e.g. Raspberry Pi)

## Usage

1. Adjust the following values if needed:
- `I2C_BUS` – I²C bus number. Check with `i2cdetect -l` or `ls /dev/i2c-*`.
- `INA219_ADDR` – INA219 I²C address. Verify with `i2cdetect -y <bus>`.
- `SHUNT_RESISTOR_OHMS` – Shunt resistor value (Ω) used on the board.
- `MAX_EXPECTED_AMPS` – Maximum expected load current (A).

For the battery percentage calculation, adjust:

- `ASSUMED_v_AT_100` – Battery voltage at 100% state of charge.
- `ASSUMED_v_AT_0` – Battery voltage at empty.

2. Run:

   ```bash
   python3 main.py
   ```
