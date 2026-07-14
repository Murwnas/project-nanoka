# project-nanoka
![KiCad 3D render](/assets/3d-render.png)

Project Nanoka is a Raspberry Pi Pico based audio output/input PCB. It exposes two audio terminals (input and output) as well as seven general-purposes input/output lines for external control. 

The PCB can be powered either through the Raspberry Pi's USB port, or through the power terminal. This requires a power module (also hosted on GitHub).

Right now, this is a prototype, and it's usefulness likely applies only to me. There are better solutions out there. I mainly created this to learn KiCad, and more broadly, PCB design which was always an interest of mine. This PCB should not be reproduced for your own personal use. If you do use it, **all responsibility is yours**. 

In this version, I want to improve Nanoka mainly through this plan:
1. Use a muxer IC to mix audio.
2. Switch from PWM audio to I2C audio for a cleaner signal.
3. Maybe re-design with SMD components to make this signafinantly smaller and elegant (but the THT components make it easier to assemble).
