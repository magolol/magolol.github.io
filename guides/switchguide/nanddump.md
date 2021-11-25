**Dumping nand**

Dumping your nand is a highly recommended step everyone should take when booting switch CFW for the first time. It is a full rip of your eMMC/sysMMC/NAND image that can be used to reflash if anything terrible happens.** 

On unpatched and unpatched systems, switch CFW gives us full access to the very early boot process.

**Please note that in the future restoring an outdated BOOT0/1 can break things, especially on Mariko/patched Erista. It is recommend to make new dumps of BOOT0/1 when updating**

**If you aren't already booted into hekate, please do so now.**

Naviagte to the `Tools` tab inside hekate. Then tap on `Backup eMMC`

Select `eMMC BOOT0 & BOOT1` 

**BOOT0/1 don't take a very long time to dump.**

Once finished, select `Close` and tap on `Backup eMMC` again. This time, select `eMMC RAW GPP`

**RAW GPP takes quite a while. Please be patient.**

Once finished, it is **highly** advised you copy the `backup` folder on the root of your SD to somewhere 100% safe. 

**To restore your nand backup, simply copy the `backup` folder back to your SD and navigate to the `Restore eMMC` option inside hekate's `Tools` tab.**

**If you're ready to move onto creating an emuMMC, you can [continue to formatting the SD for emuMMC.](https://magolol.github.io/guides/switchguide/emummccreation)**

**If you don't want to make an emuMMC, you can [continue to booting Atmosphere](https://magolol.github.io/guides/switchguide/bootingatmosphere)

**[Return to main page](https://magolol.github.io)**

**[Return to guides](https://magolol.github.io)**





