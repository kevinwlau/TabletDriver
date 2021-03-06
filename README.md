# TabletDriver

Currently the driver only works when the TabletDriverGUI is running.

The GUI minimizes to system tray / notification area.

You can reopen the GUI by double clicking the system tray icon.


#### Supported tablets:
  - Wacom CTL-470
  - Wacom CTL-471
  - Wacom CTL-472
  - Wacom CTL-480
  - Wacom CTH-480
  - Wacom CTL-490
  - XP Pen G430
  - XP Pen G640
  - Huion 420
  - Huion H640P
  - Gaomon S56K
  
#### Configured, but not properly tested:
  - Huion H420
  - Wacom CTH-470
  - Wacom CTH-670
  - Wacom CTL-671
  - Wacom CTL-672
  - Wacom CTL-680
  - Wacom CTH-680
  - Wacom CTH-490
  - Wacom PTH-451


#

#### Download

* http://hwk.fi/TabletDriver/TabletDriverV0.0.13.zip

#

#### Install

1. You might need to install these libraries, but usually these are already installed:
* https://aka.ms/vs/15/release/vc_redist.x86.exe
* https://aka.ms/vs/15/release/vc_redist.x64.exe
* https://www.microsoft.com/en-us/download/details.aspx?id=53587 (x64 and x86)

2. Unzip the driver to a folder (Shorter path is recommended, for example C:\Temp\TabletDriver)
3. Uninstall all other tablet drivers.
4. Run "install_vmulti_driver.bat". It might need a restart if there is another vmulti driver installed.
5. If you have Huion or Gaomon tablet, you need to run "install_huion_64.bat", which is located at the "driver_huion" directory.
6. Start the TabletDriverGUI.exe


#### Uninstall
1. Run "remove_vmulti_driver.bat"
2. Run "remove_huion_64.bat", which is located at the "driver_huion" directory.

#

#### VMulti and Huion drivers

If you want to compile the code and don't want to install anything from the TabletDriver binary package, you will need extract the missing drivers from these installation packages:

**VMulti driver:**
- https://www.xp-pen.com/upload/download/20180130/XP-PenWin(20180130).zip

**Huion WinUSB driver:**
- https://www.huiontablet.com/drivers/WinDriver/HuionTablet_WinDriver_v13.15.16.zip

#

#### Changelog

>**v0.0.13:**
> - Added a direction indicator to the tablet area and moved the aspect ratio text to the middle of the area.
> - TabletDriverService process priority class is now set to "High" (suggestion by /u/Devocub)
> - TabletDriverService stability and error handling improvements (thanks to https://github.com/freakode)
> - New tablet configurations: Huion H420 (made by /u/uyghti)
> - Automatically generated Wacom tablet configurations (config\wacom.cfg)

>**v0.0.12:**
> - Added multi-instance prevention. Old TabletDriverGUI.exe should pop up if you try to open another one.
> - New tablet configurations: Wacom CTL-680 and CTH-680

>**v0.0.11:**
> - Fix for DPI scaling problems. Screen mapping were wrong when the monitor DPI scaling wasn't 100%
> - Added a Wacom area tool. It should work with Wacom Intuos and Bamboo tablets (470->490)
> - Added startup debug log

>**v0.0.10:**
> - New tablet configurations: Wacom CTH-470, CTH-670, PTH-451
> - Fix for the smoothing filter. The filter didn't turn on when the settings were applied.
> - Fix for the Huion H640P clicking problem and also added better data validation for Huion 420,
>   Gaomon S56K, XP Pen G430 and G640.
> - Modified click detection on CTL-490 and CTH-490 (tablet.cfg ClickPressure).

>**v0.0.9:**
> - Yet another fix for the clicking problem... Maybe this time it will work?

>**v0.0.8:**
> - Another fix for pen tip clicking. Improved the tablet data validation.

>**v0.0.7:**
> - Added aspect ratio text to screen and tablet area.
> - Workaround for pen tip click detection. Some tablets don't send correct button data, so the pen tip click is now detected from the pressure data

>**v0.0.6:**
> - Improved smoothing filter latency calculation

>**v0.0.5:**
> - Added Windows Ink mode with pressure sensitivity
> - Added relative mouse mode
> - Added tablet area rotation
> - Added optional smoothing filter

>**v0.0.4:**
> - Fixed a number conversion bug in the tablet area detection.