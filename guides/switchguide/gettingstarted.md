**Getting Started**

**What you will need**
-Common sense

-An unpatched switch, regardless of firmware version
- If you have a chipped switch, use that instead (duh)

-An [RCM Jig](https://magolol.github.io/guides/switchguide/extras/jigs)

-A microSD of 64GB in capacity formatted as Fat32 (not exactly neccessary but **highly** recommended)

-A PC

-A USB C cable, doesn't have to be C-C so long as you can connect your switch to your device

-The latest release of hekate

**Downloads**
[Rufus](https://rufus.ie/en/) 

-This is a tool used for SD formatting on windows. Select non-bootable, MBR, Fat32, and format. Easy as that.

[Hekate](https://github.com/CTCaer/hekate/releases/latest)

[SX Gear](https://web.archive.org/web/20210217231219/https://sx.xecuter.com/download/SX_Gear_v1.1.zip) 

-Only neccessary if you're on an authentic SX Core/Lite using stock modchip firmware

**Sending the payload**

**a. Unpatched switch**

**Enter RCM by doing the following**

-Fully shut off the system
- Now would be a good time to eject the SD card and insert it into your PC ;)

-Insert the jig

-Press and hold volume up. While holding volume up, tap the power button

The screen should remain blank with no backlight. Connect your switch to your PC. Assuming you use windows, launch TegraRCMgui and download the driver when prompted. 
(If not prompted, go to settings -> Install Driver. Restart the app afterwards if needed)

If you use a device other than a windows device, please read [this guide](https://magolol.github.io/guides/switchguide/extras/rcmforotherdevices) for further instructions.

Navigate to the `hekate_ctcaer_x.x.x_Nyx_x.x.x.zip` you downloaded and extract the `hekate_ctcaer_x.x.x.bin` file to somewhere where you can access it. 

Extract the `bootloader` folder to the root of your SD card.

Inside the `bootloader` folder, create a file titled `hekate_ipl.ini`. Open it and paste the following contents inside:

`[config]
autoboot=0
autoboot_list=0
bootwait=3
backlight=100
autohosoff=0
autonogc=1
updater2p=0
bootprotect=0

[Atmosphere]
payload=bootloader/payloads/fusee.bin
icon=bootloader/res/icon_payload.bmp`

Safely eject the SD card and insert it into your switch. You can freely remove and insert the SD while inside RCM

Once tegra reports RCM OK, inject the payload. Hekate should now appear on the screen.

If nothing changes on the screen, check the following:
-The SD is formatted as Fat32
-If the stack was smashed with a 0x0000 byte setup, you have a patched switch. 
-If the stack was smashed with anything in between 0x0001 or 0x6999, you're unpatched but the injection failed.
- Change the USB cable and/or port and try again, restart tegra and/or your pc if that didn't do the trick.

**b. Chipped switch (Spacecraft-nx/hwfly)**

Assuming you've only just now installed the modchip, you'll be seeing a NO SD screen when you attempt to boot the device. This is good behavior, assuming you have no `payload.bin` on the SD. 

Press the power button again to shut off the system
Eject your SD card and insert it into your PC

Extract the `bootloader` folder and `hekate_ctcaer_x.x.x.bin` file from the `hekate_ctcaer_x.x.x_Nyx_x.x.x.zip` to the root of your SD. Rename `hekate_ctcaer_x.x.x.bin` to `payload.bin`

Inside the `bootloader` folder, create a file titled `hekate_ipl.ini`. Open it and paste the following contents inside:

`[config]
autoboot=0
autoboot_list=0
bootwait=3
backlight=100
autohosoff=0
autonogc=1
updater2p=0
bootprotect=0

[Atmosphere]
payload=bootloader/payloads/fusee.bin
icon=bootloader/res/icon_payload.bmp`

If you're on a mariko switch, add the following:

`[Warmboot Error Fix]
fss0=atmosphere/package3
stock=1
emummc_force_disable=1
icon=bootloader/res/icon_switch.bmp`


Safely eject the SD card and insert it into your switch, then press the power button. The modchip LED should hopefully flash green shortly before hekate loads on the screen.

If you're still getting the NO SD alert, make sure you did the following:

-Formatted the SD as Fat32

-Renamed the hekate payload

-That the SD card slot reader is clean and seated properly

**c. Chipped switch (SX gear)**

Assuming you've only just now installed the modchip, you'll be seeing a `boot.dat`? screen when you attempt to boot the device. This is good behavior, assuming you have no `boot.dat` on the SD. 

Press the power button again to shut off the system

Eject your SD card and insert it into your PC

Extract the `bootloader` folder and `hekate_ctcaer_x.x.x.bin` file from the `hekate_ctcaer_x.x.x_Nyx_x.x.x.zip` to the root of your SD. Rename `hekate_ctcaer_x.x.x.bin` to `payload.bin`

Extract the `boot.dat` and `boot.ini` files from the `SX_Gear_v1.1.zip` to the root of your sd.

Inside the `bootloader` folder, create a file titled `hekate_ipl.ini`. Open it and paste the following contents inside:

`[config]
autoboot=0
autoboot_list=0
bootwait=3
backlight=100
autohosoff=0
autonogc=1
updater2p=0
bootprotect=0

[Atmosphere]
payload=bootloader/payloads/fusee.bin
icon=bootloader/res/icon_payload.bmp`

If you're on a mariko switch, add the following:

`[Warmboot Error Fix]
fss0=atmosphere/package3
stock=1
emummc_force_disable=1
icon=bootloader/res/icon_switch.bmp`

Safely eject the SD card and insert it into your switch, then press the power button. The modchip LED should hopefully flash green shortly before hekate loads on the screen.

If you're still getting the `boot.dat`? alert, make sure you did the following:

-Formatted the SD as Fat32

-Renamed the hekate payload

-That the SD card slot reader is clean and seated properly

Once in hekate, you have a few options.

**First and foremost, you should make a nand backup. [Continue to making a nand backup](https://magolol.github.io/guides/switchguide/nanddump)**

**-while not 100% needed, it's very much recommended you do so.**

**If you don't want to make a nand backup for whatever reason but want an emuMMC, that is also an option. (but, if you're gonna spend the time to make an emummc, why not just make a damn backup?)**

**Either way, if you just want to make an emuMMC before a backup, you can [continue to formatting the SD for emuMMC.](https://magolol.github.io/guides/switchguide/emummccreation)**

**-while not 100% needed, emuMMC is highly recommended for safety and [helping prevent bans.](https://magolol.github.io/guides/switchguide/switchbanprotection)**

**If safety and bans aren't concerns of yours, you can [continue to booting atmosphere](https://magolol.github.io/guides/switchguide/bootingatmosphere)**

**[Return to main page](https://magolol.github.io)**

**[Return to guides](https://magolol.github.io)**
