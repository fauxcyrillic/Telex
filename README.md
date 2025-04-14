# AE-Telex
Monome Teletype for the AE modular ecosystem

![Telex v1.3](https://github.com/fauxcyrillic/AE-Telex/blob/main/Images/tt.JPG)

Work in progress, first version seems to tentatively work pretty well.
Not too many major changes required, as most of the Teletype innards run off a regulated 5v / 3.3v anyway. Changed the op-amp scaling as appropriate for a 0-5v world. Still, recreating the whole schematic from scratch was quite a task!

Loads of testing required before this is a confirmed 'thing', but feel free to take, inspect, and improve as you wish.

# Updates v1.6 (Apr 2025)

I'm putting this on the back burner indefinitely. Anyone is more than welcome to iterate on it from here. It is possible I'll return to this at some point.

As it stands, Telex is at least 95% working perfectly. The remaining issue, which I just can't solve, is the OLED seemingly drawing enough power to make other modules on the bus cable unstable, eg. oscillators go slightly out of tune when lots is happening on the OLED. My most recent attempt to mitigate this was to power the display directly from 12V using a boost circuit (in earlier versions it was powered from 3.3V, as in the Monome original module). In theory and according to the Newhaven Display datasheet, this hugely reduces current draw; I really thought this would help, but it didn't. Alas, my current knowledge of electrical engineering is not strong enough to track down the cause of this, and after something like four prototypes I can't justify spending more time and £££ on it for now. It is frustratingly close to completion! If you're a whiz with electronics and can solve this, do let me know.

I've updated this repo with the most recent gerbers and schematics, for reference.

# Updates v1.3 (Feb 2024)

Tested with a basic non-backlit keyboard; much better performance (no crashing, lower background noise)

Complete re-trace: switched from 2-layer to 4-layer PCB, making a much closer replication of the Monome design, including large copper pours for GND, AGND, 3V3 etc.

Fixed an issue with the resistor network which was messing up inputs 2 and 7

SMD resistors for LEDs

Moved I2C connection

Removed RF filter on screen (to test)

Moved decoupling caps for DAC and ADC much closer to ICs (to test, hopefully a big improvement)

Tidied up around the USB power driver chip, also moved it to the front of the board (was getting in the way of the AE bus cable when underneath)

Tweaks to front panel: improved cutout tolerances, font sizes etc


# Observations so far (late 2023)

Works ok with my RK61 keyboard as long as I *connect the Telex end of the usb cable first*. Turned the backlight off (although it seems fine with it on)

Had a couple (2) of 'crashes' (screen went off, scripts still running, had to power-cycle rack), at least one of which might be related to me messing with the keyboard connection during use as above

On the other hand, I've also had a number of long sessions with no issues at all; will continue to monitor to judge frequency

Reading the IN jack with nothing connected reads a value in the region of 50-60 even after calibration. Not sure if this is normal, and there's no reason to read it without a connection anyway. When patched the GND it reads 0 correctly

Not sure of the correct procedure for loading scenes with the onboard button so can't say if its working as expected. Are you supposed to hold it down when scrolling?

TO DO / IN PROGRESS: tighten up some panel tolerances (around sockets and USB jack)

TO DO: adjust code to max at 5v? Will test to see if necessary

TO DO: confirm best way to connect OLED

TO DO: Test with a bigger cap on power (330 or 470uF)

TO DO: check neccessity of cap before screen - bigger? smaller? Not needed at all?
