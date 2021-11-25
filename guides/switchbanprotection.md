**A brief explanation before we get into it/establishing canonical backstory**

The switch is a very easy system to get CFW running on so long as you have an exploitable system. Read [this](https://ismyswitchpatched.com) and [this](switchgui.de) for more info.
But while hacking the system and installing unauthorized software is very easy, the switch is notorious for having a ton of telemetry which can result in a permanent system ban from all online services.
We have many ways to prevent bans and block telemetry, and it is highly suggested you take all measures before continuing with anything switch related.

emuMMC is a fantastic way to prevent bans when utilized properly, but it is not by itself perfect. But with a little bit of work, we can make it nearly perfect.

What will get you banned

- Modifying Online Games
	- Cheating in online games
    - Using mods in online games
    - Editing save files for online games
- Making modifications to your sysMMC
    - Installing nsp/*nsz/xci/xcz files
		- Installing homebrew forwarders OR backups (even if you legitimately dumped them!) will get you banned. 
- Clearing logs after they've been sent (this applies to both sysMMC and emuMMC)
    - Running anything to modify your sysMMC
	- Using a custom user picture
- Doing the above points on emuMMC without using:
	- Exosphere/Incognito
	- dns.mitm

**Please note we will be doing semi permanent measures. While the chances of your hardware being damaged are very small, this guide and it's afilliates assume no responsibility if something goes wrong. Blame yourself, your eyes, your hands, your brain, etc.**
**ALWAYS MAKE A BACKUP. THE BEST BACKUP IS THE ONE YOU MADE BUT NEVER NEED, WHILE THE WORST ONE IS THE ONE YOU NEED BUT NEVER MADE.**

**DO NOT BLAME US. YOU HAVE BEEN WARNED**

**Downloads**

(Optional but recommended) [Tinfoil](https://tinfoil.io/Download#download) (you can choose between which option)
[90DNS tester](https://github.com/meganukebmp/Switch_90DNS_tester/releases/latest)

**1. Creating exosphere**

Start off by creating a file named exosphere.ini on the root of your SD and paste the following:

**This assumes you are using emuMMC:**
	
```INI
[exosphere]
debugmode=1
debugmode_user=0
disable_user_exception_handlers=0
enable_user_pmu_access=0
blank_prodinfo_sysmmc=0
blank_prodinfo_emummc=1
allow_writing_to_cal_sysmmc=0
log_port=0
log_baud_rate=115200
log_inverted=0
```

**2. Creating dns.mitm**

Create a file named `emummc.txt` in `/atmosphere/hosts/` (the `hosts` folder might not exist, so make sure to create it if it's absent) 
and paste this in your `emummc.txt` file:

`# Block Nintendo Servers
127.0.0.1 *nintendo.*
127.0.0.1 *nintendo-europe.com
127.0.0.1 *nintendoswitch.*
95.216.149.205 *conntest.nintendowifi.net
95.216.149.205 *ctest.cdn.nintendo.net`

**3. Checking if everything worked**

Once you're finished creating dns.mitm and exosphere, download the switch 90DNS tester `.nro` file. Copy it to the switch folder on your SD card. 
Exit out of the SD and safely eject it. Reinsert it to your system and boot atmosphere. 

Once in the OS, run the 90dns tester from the homebrew menu. With any luck, all links will be blocked. Restart your device and verify that exosphere is working by going into your Switch's Settings ➞ System ➞ Serial Information. You should see that your serial number will look something like XAW00000000000.

**4. (Optional) Installing permanent incognito through Tinfoil**

!!DO NOT RUN TINFOIL UNTIL YOU HAVE 100% CONFIRMED THE SYSTEM ISN'T REACHING NINTENDO!!

If you happen to be running on a Mariko unit, DO NOT FOLLOW THIS STEP.

Assuming you already have tinfoil installed, launch it and navigate to the Incognito tab near the bottom.
Highlight your serial number in the right space and press Y. Tinfoil will warn you about the consequences if you forget your password.
Either set the password as nothing or something simple that you are not going to forget. Should you forget your password, you will be able to pull this back from your NAND backup, worst case.

If done correctly, Tinfoil will report writing to CAL0 was successful. Reboot the system. Verify incognito has been enabled correctly by doing the same process as listed in step 3.

Incognito is **permanent,** and relies on no files to stay active. It's best usecase is as a fail safe. 

[Return to main page](https://magolol.github.io)

[Return to guides](https://magolol.github.io)

