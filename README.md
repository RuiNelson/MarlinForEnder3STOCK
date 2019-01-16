# MarlinForEnder3STOCK

Marlin for the 100% Stock Ender 3

Original at: http://marlinfw.org, this is a fork

This is version 1.1.9

## It Features Compared to the Original Firmware

* **Thermal Runaway Protection**
* **Individual Axis Homing**
* **Level Bed Corners Assist (thumb screws assist)**
* **Bilinear Bed Leveling (Manual)**
Note: it is configured to maintain the bed leveling between prints, but will go away when you power off the machine, you'll need to "Save" and "Load" the configuration. You should add a line containing `G29` in your starting GCode after your `G28` (home), [you can use my start/end GCODE](https://github.com/RuiCarneiro/MarlinForEnder3STOCK/blob/master/Cura%20and%20Slic3r%20GCODEs.md).
* **Babystep Z**
* **S-Curve Acceleration**
* **PID Autotune menu for the hotend and save to memory**
* **Pre-heat PLA and ABS temperatures Configuration**
* **Fan kick-off**
In the stock firmware, if you select a low fan speed (e.g. 20%), the fan probably won't spin at all, because the current isn't enough for the fan to overcome the initial intertia, I've set the fan to spin at full power during 0.8 seconds to allow for lower fan speeds.

I wish I could add more, but there's no space left in the microcontroller.

## Sacrifices that have been made compared to the Original Firmware

This firmware takes 129,634 bytes of the availiable 130,048 bytes of program memory the microcontroller has after installing the Arduino bootloader, so some sacrifices had to be made:

* No power on image (dragon), or that "Ender 3" logo you see are gone
* The Buzzer can only do beeps at a single frequency
* The fan animation in the screen is gone, the fan works and you see the percentage, but doesn't spin
* No resume after power loss option
* All text is at the same size (there's no big text when entering a value, and the "info screen" text is all the same size)
* `M503` (Report Settings) command deleted (not usefull when you have the source code and the menus)

## Some user Options

### You can disable the beep of the buzzer when using menus

Edit Configuration.h (example in the Arduino IDE) and change the values of `LCD_FEEDBACK_FREQUENCY_DURATION_MS` and `LCD_FEEDBACK_FREQUENCY_HZ` to zero (`0`)




