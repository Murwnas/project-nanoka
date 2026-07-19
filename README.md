# project-nanoka
![KiCad 3D render](/assets/3d-render.png)

Project Nanoka is a Raspberry Pi Pico based audio output/input PCB. It exposes two audio terminals (input and output) as well as seven general-purposes input/output lines for external control. 

The PCB can be powered either through the Raspberry Pi's USB port, or through the power terminal. This requires a power module, which is also hosted on GitHub.

This version has several improvements over v1.2:
1. SD card support. We no longer rely on the small flash chip, which is very limited in space, especially when CircuitPython is used for firmware.
2. A Texas Instruments i2c DAC instead of lower quality PWM audio.
3. Stereo audio! Both on input and output
4. An analogue switch IC to output between the board input audio (for external sources) and the DAC's PCM output (internal Pico audio). No more noisy relays. 
5. Mostly SMD components, which makes the board cheaper.

This has not been produced and tested yet, so assume it has issues. It did take me two tries for v1 to work properly.


