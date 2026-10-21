# notastarboy

![notastarboy render](image-1.png)

notastarboy is a motion-controlled desktop pet that remembers you. It's project that i made by following the Starbie Week 1 guide, it has same hardware, same tilt-to-select menu, but instead of just saving three stat numbers, it keeps a log of your last 16 interactions + lifetime totals, all stored in the flash meomory so they survive a reboot. A new MOOD view reads that log and calls the pet out if you've been ignoring it.

## What it is

notastarboy sits on your desk, shows its personality on a small OLED, and reacts to how you handle it. Tilting opens a radial menu (NAP / PLAY / FEED / PET), shaking does a quick stat bump on its own. Everything still runs on a microcontroller, display, motion sensor, and environmental sensor in a compact through-hole PCB.

What's different from stock Starbie: every action gets logged, not just applied and forgotten. Press button 2 twice to pull up the MOOD view and see FED / PLAYED / NAPPED / PET / SHAKEN totals, how many entries are currently logged, and a one-word callout (HUNGRY / BORED / LONELY) if you've left one stat untouched for 6+ hours.

<img width="1382" height="810" alt="image" src="https://github.com/user-attachments/assets/f0fc3b82-3c3e-4a11-a5cb-13b7059c559a" />


### Bill of materials(BOM)

| Item | Description | Qty | Unit Price (AUD) | Line Total (AUD) | Link |
|------|-------------|-----|------------------|------------------|------|
| 1 | Beetle ESP32-C3 (RISC-V Core Development Board), main microcontroller for all the processing | 1 | $8.50 | $8.50 | [Link](https://robocraze.com/products/beetle-esp32-c3-risc-v-core-development-board?_pos=1&_psq=esp32+c3&_psid=18ba7251c&_ss=e) |
| 2 | MPU6050, gyroscope and motion detection | 1 | $1.70 | $1.70 | [Link](https://robocraze.com/products/mpu-6050-triple-axis-accelerometer-gyroscope-module?_pos=1&_psq=MPU6050&_psid=26e4c4fb9&_ss=e) |
| 3 | DHT11, environment sensing | 1 | $0.70 | $0.70 | [Link](https://robocraze.com/products/dht11-humidity-and-temperature-sensor?_pos=2&_sid=9e06e5b0b&_ss=r) |
| 4 | 0.96" OLED Display, display for showing main pet | 1 | $1.80 | $1.80 | [Link](https://robocraze.com/products/0-96in-oled-display-module-4pin?_pos=1&_psq=0.96+OLED&_psid=bfed60e23&_ss=e) |
| 5 | Resistors, resistors for resisting current | 1 | $0.50 | $0.50 | [Link](https://robocraze.com/products/resistor-box?_pos=1&_sid=7e886e4f5&_ss=r) |
| 6 | MX Switches, for interaction | 1 | $5.17 | $5.17 | [Link](https://www.amazon.in/Buildcon-Mechanical-Keyboard-Universal-Keyboards/dp/B0GCCQLQBV/) |
| 7 | Keycaps, keycaps for switches | 1 | $11.00 | $11.00 | [Link](https://www.amazon.in/ZORBES-130-Key-Topographic-Mechanical-Keyboard/dp/B0GZMBPHYB/) |
| 8 | Tax and shipping for the whole order | – | – | $0.63 | – |
| | **Total** | | | **$30.00** | |


## Why?

This started as the week 1 beginner tutorial for halflife. The journal is the required departure from the guide, Starbie's own maintainers ask that submissions change more than the shape, so this adds actual firmware behavior on top instead of reskinning the same build.

## Software

`notastarboy.ino` is the self contained sketch i found in the guide and i added some changed to it so that mood+storage/interactions gets added as well, its not much but its not less as well.

## Known issues

A few cosmetic DRC warnings remain (silkscreen clipped by solder mask/board edge on the back graphic, J1's courtyard excluded since it's an imported footprint). None affect routing, copper, or manufacturability, see DRC reports in this repo for the full list.
