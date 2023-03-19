<p align="center"><img src="buildroot/share/pixmaps/logo/marlin-outrun-nf-500.png" height="250" alt="MarlinFirmware's logo" /></p>

<h1 align="center">Marlin 3D Printer Firmware</h1>

<p align="center">
    <a href="/LICENSE"><img alt="GPL-V3.0 License" src="https://img.shields.io/github/license/marlinfirmware/marlin.svg"></a>
    <a href="https://github.com/MarlinFirmware/Marlin/graphs/contributors"><img alt="Contributors" src="https://img.shields.io/github/contributors/marlinfirmware/marlin.svg"></a>
    <a href="https://github.com/MarlinFirmware/Marlin/releases"><img alt="Last Release Date" src="https://img.shields.io/github/release-date/MarlinFirmware/Marlin"></a>
    <a href="https://github.com/MarlinFirmware/Marlin/actions"><img alt="CI Status" src="https://github.com/MarlinFirmware/Marlin/actions/workflows/test-builds.yml/badge.svg"></a>
    <a href="https://github.com/sponsors/thinkyhead"><img alt="GitHub Sponsors" src="https://img.shields.io/github/sponsors/thinkyhead?color=db61a2"></a>
    <br />
    <a href="https://fosstodon.org/@marlinfirmware"><img alt="Follow MarlinFirmware on Mastodon" src="https://img.shields.io/mastodon/follow/109450200866020466?domain=https%3A%2F%2Ffosstodon.org&logoColor=%2300B&style=social"></a>
</p>

Additional documentation can be found at the [Marlin Home Page](https://marlinfw.org/).
Please test this firmware and let us know if it misbehaves in any way. Volunteers are standing by!

## Marlin 2.1 Bugfix Branch

__Not for production use. Use with caution!__

Marlin 2.1 takes this popular RepRap firmware to the next level by adding support for much faster 32-bit and ARM-based boards while improving support for 8-bit AVR boards. Read about Marlin's decision to use a "Hardware Abstraction Layer" below.

This branch is for patches to the latest 2.1.x release version. Periodically this branch will form the basis for the next minor 2.1.x release.

Download earlier versions of Marlin on the [Releases page](https://github.com/MarlinFirmware/Marlin/releases).

## Example Configurations

Before you can build Marlin for your machine you'll need a configuration for your specific hardware. Upon request, your vendor will be happy to provide you with the complete source code and configurations for your machine, but you'll need to get updated configuration files if you want to install a newer version of Marlin. Fortunately, Marlin users have contributed dozens of tested configurations to get you started. Visit the [MarlinFirmware/Configurations](https://github.com/MarlinFirmware/Configurations) repository to find the right configuration for your hardware.

## Building Marlin 2.1

To build and upload Marlin you will use one of these tools:

- The free [Visual Studio Code](https://code.visualstudio.com/download) using the [Auto Build Marlin](https://marlinfw.org/docs/basics/auto_build_marlin.html) extension.
- The free [Arduino IDE](https://www.arduino.cc/en/main/software) : See [Building Marlin with Arduino](https://marlinfw.org/docs/basics/install_arduino.html)
- You can also use VSCode with devcontainer : See [Installing Marlin (VSCode devcontainer)](http://marlinfw.org/docs/basics/install_devcontainer_vscode.html).

Marlin is optimized to build with the **PlatformIO IDE** extension for **Visual Studio Code**. You can still build Marlin with **Arduino IDE**, and we hope to improve the Arduino build experience, but at this time PlatformIO is the better choice.

## Hardware Abstraction Layer (HAL)

Marlin includes an abstraction layer to provide a common API for all the platforms it targets. This allows Marlin code to address the details of motion and user interface tasks at the lowest and highest levels with no system overhead, tying all events directly to the hardware clock.

Every new HAL opens up a world of hardware. At this time we need HALs for RP2040 and the Duet3D family of boards. A HAL that wraps an RTOS is an interesting concept that could be explored. Did you know that Marlin includes a Simulator that can run on Windows, macOS, and Linux? Join the Discord to help move these sub-projects forward!

## 8-Bit AVR Boards

A core tenet of this project is to keep supporting 8-bit AVR boards while also maintaining a single codebase that applies equally to all machines. We want casual hobbyists to benefit from the community's innovations as much as possible just as much as those with fancier machines. Plus, those old AVR-based machines are often the best for your testing and feedback!

### Supported Platforms

  Platform|MCU|Example Boards
  --------|---|-------
  [Arduino AVR](https://www.arduino.cc/)|ATmega|RAMPS, Melzi, RAMBo
  [Teensy++ 2.0](https://www.microchip.com/en-us/product/AT90USB1286)|AT90USB1286|Printrboard
  [Arduino Due](https://www.arduino.cc/en/Guide/ArduinoDue)|SAM3X8E|RAMPS-FD, RADDS, RAMPS4DUE
  [ESP32](https://github.com/espressif/arduino-esp32)|ESP32|FYSETC E4, E4d@BOX, MRR
  [LPC1768](https://www.nxp.com/products/processors-and-microcontrollers/arm-microcontrollers/general-purpose-mcus/lpc1700-cortex-m3/512-kb-flash-64-kb-sram-ethernet-usb-lqfp100-package:LPC1768FBD100)|ARM® Cortex-M3|MKS SBASE, Re-ARM, Selena Compact
  [LPC1769](https://www.nxp.com/products/processors-and-microcontrollers/arm-microcontrollers/general-purpose-mcus/lpc1700-cortex-m3/512-kb-flash-64-kb-sram-ethernet-usb-lqfp100-package:LPC1769FBD100)|ARM® Cortex-M3|Smoothieboard, Azteeg X5 mini, TH3D EZBoard
  [STM32F103](https://www.st.com/en/microcontrollers-microprocessors/stm32f103.html)|ARM® Cortex-M3|Malyan M200, GTM32 Pro, MKS Robin, BTT SKR Mini
  [STM32F401](https://www.st.com/en/microcontrollers-microprocessors/stm32f401.html)|ARM® Cortex-M4|ARMED, Rumba32, SKR Pro, Lerdge, FYSETC S6, Artillery Ruby
  [STM32F7x6](https://www.st.com/en/microcontrollers-microprocessors/stm32f7x6.html)|ARM® Cortex-M7|The Borg, RemRam V1
  [STM32G0B1RET6](https://www.st.com/en/microcontrollers-microprocessors/stm32g0x1.html)|ARM® Cortex-M0+|BigTreeTech SKR mini E3 V3.0
  [STM32H743xIT6](https://www.st.com/en/microcontrollers-microprocessors/stm32h743-753.html)|ARM® Cortex-M7|BigTreeTech SKR V3.0, SKR EZ V3.0, SKR SE BX V2.0/V3.0
  [SAMD51P20A](https://www.adafruit.com/product/4064)|ARM® Cortex-M4|Adafruit Grand Central M4
  [Teensy 3.5](https://www.pjrc.com/store/teensy35.html)|ARM® Cortex-M4|
  [Teensy 3.6](https://www.pjrc.com/store/teensy36.html)|ARM® Cortex-M4|
  [Teensy 4.0](https://www.pjrc.com/store/teensy40.html)|ARM® Cortex-M7|
  [Teensy 4.1](https://www.pjrc.com/store/teensy41.html)|ARM® Cortex-M7|
  Linux Native|x86/ARM/etc.|Raspberry Pi

## Submitting Patches

Proposed patches should be submitted as a Pull Request against the ([bugfix-2.1.x](https://github.com/MarlinFirmware/Marlin/tree/bugfix-2.1.x)) branch.

- This branch is for fixing bugs and integrating any new features for the duration of the Marlin 2.1.x life-cycle.
- Follow the [Coding Standards](https://marlinfw.org/docs/development/coding_standards.html) to gain points with the maintainers.
- Please submit Feature Requests and Bug Reports to the [Issue Queue](https://github.com/MarlinFirmware/Marlin/issues/new/choose). Support resources are also listed there.
- Whenever you add new features, be sure to add tests to `buildroot/tests` and then run your tests locally, if possible.
  - It's optional: Running all the tests on Windows might take a long time, and they will run anyway on GitHub.
  - If you're running the tests on Linux (or on WSL with the code on a Linux volume) the speed is much faster.
  - You can use `make tests-all-local` or `make tests-single-local TEST_TARGET=...`.
  - If you prefer Docker you can use `make tests-all-local-docker` or `make tests-all-local-docker TEST_TARGET=...`.

## Marlin Support

The Issue Queue is reserved for Bug Reports and Feature Requests. To get help with configuration and troubleshooting, please use the following resources:

- [Marlin Documentation](https://marlinfw.org) - Official Marlin documentation
- [Marlin Discord](https://discord.gg/n5NJ59y) - Discuss issues with Marlin users and developers
- Facebook Group ["Marlin Firmware"](https://www.facebook.com/groups/1049718498464482/)
- RepRap.org [Marlin Forum](https://forums.reprap.org/list.php?415)
- Facebook Group ["Marlin Firmware for 3D Printers"](https://www.facebook.com/groups/3Dtechtalk/)
- [Marlin Configuration](https://www.youtube.com/results?search_query=marlin+configuration) on YouTube

## Contributors

Marlin is constantly improving thanks to a huge number of contributors from all over the world bringing their specialties and talents. Huge thanks are due to [all the contributors](https://github.com/MarlinFirmware/Marlin/graphs/contributors) who regularly patch up bugs, help direct traffic, and basically keep Marlin from falling apart. Marlin's continued existence would not be possible without them.

## Administration

Regular users can open and close their own issues, but only the administrators can do project-related things like add labels, merge changes, set milestones, and kick trolls. The current Marlin admin team consists of:

<table align="center">
<tr><td>Project Maintainer</td></tr>
<tr><td>

 🇺🇸  **Scott Lahteine**
       [@thinkyhead](https://github.com/thinkyhead)
       [<kbd>  Donate 💸  </kbd>](https://www.thinkyhead.com/donate-to-marlin)

</td><td>

 🇺🇸  **Roxanne Neufeld**
       [@Roxy-3D](https://github.com/Roxy-3D)

* Grab latest version (or whichever version you like) from the release section [here](https://github.com/hillsoftware/sv06/releases)
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
* Before doing any of the following steps. Make sure there is NO filament hanging out of the nozzle . The Extruder autotune done previously can cause filament to ooze out. This can cause you to get faulty calibrations when you do a Z offset or X-Twist as the dry filament will make you think you are closer to the bed that you are!
* Go to Configuration/Advanced/Probe Offsets /Z Offset Wizard (No X-Twist) & calibrate your z offset. Save settings.
## If you downloaded the UBL version follow these steps next
* Go to Motion / Unified Bed Leveling / UBL Mesh Wizard
* Let the UBL probe all the points it can. It won’t be able to do all 100. This is normal.
* Settings should autosave after UBL finishes, but you can save yourself too if you wish
## If you downloaded the bi-linear version follow these steps next
* Go to Motion / Bed Leveling / Level Bed
* Let it probe all 25 points
* When finished do a store settings to save the mesh data
## The following steps are for UBL or bi-linear versions
* Do a test print now before trying x-twist.   This is to see if the UBL or bilinear leveling is enough to compensate for your issues with first layers and such before even trying the x-twist. Make sure you have proper startup g-code to use the UBL or bi-linear mesh as mentioned below. 
* If your print is good.  Congratulations and happy printing.
* If it didn’t help enough, go ahead and run X-Twist. Configuration / Advanced / Probe Offsets / X-Twist
* IMPORTANT ! Rerun your UBL or bi-linear mesh after doing the X-Twist ( the twist doesn’t modify existing mesh data, if modifies future probed points as the UBL or bi-linear leveling does its thing )
* Save settings / Do a test print
* If your print is good, happy printing. If not, come on to the SV06 Facebook group and let us know. Pictures, detail, data, etc can help us in possibly identifying your issue and seeing if we can improve the firmware.
* Also if you find the UBL and bi-linear are not enough for your unit, you can download the manual-mesh version. This one functions like the bi-linear but you manually use the paper or feeler guage with the nozzle for the 5x5 array.  Be sure to save after.  For people who have struggled with their units getting good first layers with stock firmware, or my UBL or bi-linear version, the manual mesh has fixed their issue.  Mind you this is a manual process and takes the probe out of the picture.

 🇺🇸  **Jason Smith**
       [@sjasonsmith](https://github.com/sjasonsmith)

</td><td>

 🇧🇷  **Victor Oliveira**
       [@rhapsodyv](https://github.com/rhapsodyv)

 🇬🇧  **Chris Pepper**
       [@p3p](https://github.com/p3p)

🇳🇿  **Peter Ellens**
       [@ellensp](https://github.com/ellensp)
       [<kbd>  Donate 💸  </kbd>](https://ko-fi.com/ellensp)

* X-Twist Compensation  Compensates for a twisted X axis by having the user manually take three measurements of the nozzle to the bed and compares them to the probes calculation for that point. It then modifies all future probe points to try to compensate for the twist in the X-Axis. It is very important that after doing the twist you re-run the UBL wizard since the X-Twist values don’t change the existing mesh in memory, only as new points are probed.  Also you need to be as precise and consistent as possible when calibrating the 3 X-Twist points. It is recommended to use a feeler gauge so you can make sure each of the three points has the nozzle exactly the same distance from the bed as the others.
* X-Twist Reset Menu : A menu option was added to reset the X-Twist data and turn it off. This would be useful if you want to wipe the twist as you don’t need it, or want to try it without it. NOTE: You must save your settings if you want to make the disabling persistent after a power off. Plus you need to redo your UBL mesh.
* PID Extruder and Bed Control
* Power Loss Recover This feature is turned off by default
* Filament Runout Sensor Support This feature is turned off by default. The SV06 doesn’t come with a runout sensor, so here is a [link](https://www.printables.com/model/347596-endstop-runout-sensor) to Rory’s design for a mount to install one on your SV06
*  Z-Offset Wizard. If you don’t need the X-Twist because your X gantry isn’t twisted you can use this wizard to adjust your Z-Offset
* Rory’s tweaks

 🇺🇸  **Bob Kuhn**
       [@Bob-the-Kuhn](https://github.com/Bob-the-Kuhn)

 🇳🇱  **Erik van der Zalm**
       [@ErikZalm](https://github.com/ErikZalm)
       [<kbd>  Donate 💸  </kbd>](https://flattr.com/submit/auto?user_id=ErikZalm&url=https://github.com/MarlinFirmware/Marlin&title=Marlin&language=&tags=github&category=software)

</td></tr>
</table>

## License

Marlin is published under the [GPL license](/LICENSE) because we believe in open development. The GPL comes with both rights and obligations. Whether you use Marlin firmware as the driver for your open or closed-source product, you must keep Marlin open, and you must provide your compatible Marlin source code to end users upon request. The most straightforward way to comply with the Marlin license is to make a fork of Marlin on Github, perform your modifications, and direct users to your modified fork.

While we can't prevent the use of this code in products (3D printers, CNC, etc.) that are closed source or crippled by a patent, we would prefer that you choose another firmware or, better yet, make your own.
