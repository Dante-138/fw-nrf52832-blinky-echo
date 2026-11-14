# fw-nrf52832-blinky-echo

Two small test projects for the nRF52832 DK: a four-LED blinky and a UART echo over the J-Link VCOM. Zephyr RTOS, nRF Connect SDK.

## What it does

| Project | Behavior |
|---|---|
| `blinky-4leds` | Blinks the four LEDs together every 500 ms. |
| `vcom-echo` | Echoes back every character typed in a serial terminal. |

## Hardware

| Item | Detail |
|---|---|
| Board | nRF52832 DK (PCA10040) |
| Connection | USB cable on the J2 (DEBUG) connector |
| UART | J-Link VCOM, 115200 8N1 |

## Build

Requires nRF Connect SDK v3.0.2 or compatible. Build one project at a time:

```bash
west build -b nrf52dk/nrf52832 blinky-4leds --pristine
```

```bash
west build -b nrf52dk/nrf52832 vcom-echo --pristine
```

## Flash

```bash
west flash --runner jlink
```

## Test

- `blinky-4leds`: the four LEDs blink together.
- `vcom-echo`: open a serial terminal on the DK's COM port (115200 8N1), press RESET on the board, then type. Each character is echoed back.

## License

MIT, see [LICENSE](LICENSE).
