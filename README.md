# project-nanoka
![KiCad 3D render](/assets/3d-render.png)

Project Nanoka is a Raspberry Pi Pico based audio output/input board. It exposes two audio terminals (input and output) as well as seven general-purposes input/output lines for external control. 

The PCB can be powered either through the Raspberry Pi's USB port, or through the power terminal. This requires a power module, which is also hosted on GitHub.

This version has several improvements over v1.2:
1. SD card support. It no longer relies on the small flash chip, which is very limited in space, especially when CircuitPython is used for firmware.
2. A Texas Instruments i2s DAC instead of lower quality PWM audio.
3. Stereo audio! Both on input and output
4. Ditches the noisy relay for an analogue switch IC.
5. Mostly SMD components, which makes the board cheaper.

Consequently, the SMD components makes this much harder to hand-solder than the previous version. The old version is still capable enough (deployed in a real environment right now) so if soldering skills and/or equipment is limited, the older version might be preferable over this. 

## Real reproduction (Aivon + DigiKey)
![Picture of real board](/assets/prod.webp)

Known issues:
1. Piezo doesn't work. R6 pulls down the line too much, preventing the Pico GPIO from driving its gate properly. This can probably be fixed with a higher resistor value.
2. Missing trace to DAC's power pin. This can be band-aid fixed with a bodge wire (see picture).
3. Most SDIO drivers expect a D0+3 consecutive pin order. This has a D0-3 order. I was able to patch the no-OS-FatFS-SD-SDIO-SPI-RPi-Pico driver (great name, btw) to overcome this though.
4. Not the best SD routing. But it works fast enough for this project's purposes. Tested to perform with 9 MB/s read and 5.7 MB/s write speeds at 20 MHz.

