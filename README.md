# Sovol SV06 2.1.x bugfix build

## NOTE THIS IS HIGHLY EXPERIMENTAL FIRMWARE! USE AT YOUR OWN RISK!

### Testing steps for this firmware.

* Download firmware here  ( current version v.54 from January 19th, 2023 )
* Put binary on a fresh FAT32 formatted SD card and insert the sd card into your SV06 while it is powered off
* Boot up SV06.  It may take 10-20 seconds. Screen will flash and it should boot. The SV06 Stock board can sometimes be temperamental with sd cards & flashing, if your flash fails & you're left with a blue screen only, switch off & try another card, a new name brand with a fresh format helps.
* It should reset the eeprom when changing a major firmware, but you can config/advanced/initialize eeprom & reset too if you wish.
* Please ensure your X gantry is perfectly level to your bed , do this manually & not with the Auto Z Align function.Use two identical objects on the bed, one under each side of the gantry & lower the gantry down by hand, do not use the motors to lower it, steppers must be disabled or printer should be turned off.
* Go to Motion / Homing and select Auto Home. Watch the homing process. The X axis should go ALL the way to the left and bump up against the left side of the frame. The Y axis should go ALL the way to the back and bump into the back of the frame. If either of these don’t go all the way, or make grinding noises your sensitivity is too high or too low respectively. If you have an issue with the X axis not going all the way to the left your sensorless homing for the X is too sensitive. Likewise if it grinds loudly against the left side it is not sensitive enough. Go to Configuration / Advanced / TMC Drivers / Sensorless Homing.  Go to the axis you need to tweak (X or Y). If your X axis stops before hitting the left side you are too sensitive on X.  So lower the X value by 5 and retry homing. If your X grinds too much for instance on the left side, you are sensitive enough so raise the X value by 5. Use the same process for Y if it has issues. Once you tweak the values to your liking, be sure to save settings so they persist reboots.
* Autotune PID.  Configuration / Advanced / Temperatures / PID Autotune Extruder (wait for finish). Be aware this can take awhile
* The way to tell PID tune is done is your hotend will be cooling down to room temp. 
* Store Settings is a good idea here incase of reboot
* Autotune Bed PID Configuration / Advanced / Temperatures / PID Autotune Bed (wait for finish)
* Store Settings is a good idea here incase of reboot
* Before doing any of the following steps. Make sure there is NO filament hanging out of the nozzle . The MPC calibration done previously can cause filament to ooze out. This can cause you to get faulty calibrations when you do a Z offset or X-Twist as the dry filament will make you think you are closer to the bed that you are!
* Go to Configuration/Advanced/ProbeWizard/Z Offset Wizard (No X-Twist) & calibrate your z offset. Save settings.
* Go to Motion / Unified Bed Leveling / UBL Mesh Wizard ( Rory's Video  for info on that)
* Let the UBL probe all the points it can. It won’t be able to do all 100. This is normal.
* Settings should autosave after UBL finishes, but you can save yourself too if you wish
* Do a test print now before trying x-twist.   This is to see if the UBL is enough to compensate for your issues with first layers and such before even trying the x-twist. Make sure you have proper startup g-code to use the UBL mesh as mentioned in Rory’s video linked above and below. This is also noted in the UBL section on the next page.
* If your print is good.  Congratulations and happy printing.
* If it didn’t help enough, go ahead and run X-Twist. Configuration / Advanced / Probe Wizard / X-Twist
* IMPORTANT ! Rerun UBL after doing the X-Twist ( the twist doesn’t modify existing mesh data, if modifies future probed points as the UBL does its thing )
* Save settings / Do a test print
* If your print is good, happy printing. If not, come on to the SV06 Facebook group and let us know. Pictures, detail, data, etc can help us in possibly identifying your issue and seeing if we can improve the firmware

## Firmware Features Used

* Unified Bed Leveling  (UBL) an optimized leveling feature that stores a high data point mesh in non-volatile storage. In your startup G-Code you just have it do a 9 point quick probe to figure out the tilt of the bed, and the high resolution mesh is adjusted.
*  Add the following to your Gcode in your slicer after the G28 and after your printer has heated up to temp, but before any print starts.  This will load your mesh and do that 9 point measurement to determine how to adjust the mesh if needed.

```
G29 A ; Unified bed-level (BL-Touch)
G29 L0 ; Load Mesh Slot 0
G29 J3 ; Probe 9 points to check mesh
```

* X-Twist Compensation  Compensates for a twisted X axis by having the user manually take three measurements of the nozzle to the bed and compares them to the probes calculation for that point. It then modifies all future probe points to try to compensate for the twist in the X-Axis. It is very important that after doing the twist you re-run the UBL wizard since the X-Twist values don’t change the existing mesh in memory, only as new points are probed.  Also you need to be as precise and consistent as possible when calibrating the 3 X-Twist points. It is recommended to use a feeler gauge so you can make sure each of the three points has the nozzle exactly the same distance from the bed as the others.
* X-Twist Reset Menu : A menu option was added to reset the X-Twist data and turn it off. This would be useful if you want to wipe the twist as you don’t need it, or want to try it without it. NOTE: You must save your settings if you want to make the disabling persistent after a power off. Plus you need to redo your UBL mesh.
* PID Extruder and Bed Control
* Power Loss Recover This feature is turned off by default
* Filament Runout Sensor Support This feature is turned off by default. The SV06 doesn’t come with a runout sensor, so here is a link to Rory’s design for a mount to install one on your SV06
*  Z-Offset Wizard. If you don’t need the X-Twist because your X gantry isn’t twisted you can use this wizard to adjust your Z-Offset
* Rory’s tweaks
