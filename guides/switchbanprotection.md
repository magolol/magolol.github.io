**A brief explanation before we get into it/establishing canonical backstory**

The switch is a very easy system to get CFW running on so long as you have an exploitable system. Read [this](https://ismyswitchpatched.com) and [this](switchgui.de) for more info.
But while hacking the system and installing unauthorized software is very easy, the switch is notorious for having a ton of telemetry which can result in a permanent system ban from all online services.
We have many ways to prevent bans and block telemetry, and it is highly suggested you take all measures before continuing with anything switch related.

EmuMMC is a fantastic way to prevent bans when utilized properly, but it is not by itself perfect. But with a little bit of work, we can make it nearly perfect.

#####What will get you banned
***
- Modifying Online Games
	- Cheating in online games
    - Using mods in online games
    - Editing save files for online games
- Making modifications to your SysNAND.
    - Installing **nsp**/**nsz**/**xci**/**xcz** files.
		- Installing homebrew forwarders will get you banned.
		- Installing game backups will get you banned.
    - Running nro's that modify your SysNAND (Tinfoil Installer, incognito, etc.)
	- Using a custom user picture
- Doing the above points on EmuMMC without using:
	- Exosphere/Incognito
	- dns.mitm

**Please note we will be doing semi permanent measures. While the chances of your hardware being damaged are very small, this guide and it's afilliates assume no responsibility if something goes wrong. Blame yourself, your eyes, your hands, your brain, etc.**
**ALWAYS MAKE A BACKUP. THE BEST BACKUP IS THE ONE YOU MADE BUT NEVER NEED, WHILE THE WORST ONE IS THE ONE YOU NEED BUT NEVER MADE.**

DO NOT BLAME US. YOU HAVE BEEN WARNED

**Downloads**

**1. Getting started**

	-Start off by creating a file named exosphere.ini on the root of your SD and paste the following:

	**For EmuNAND:**
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

[Return to main page](https://magolol.github.io)

[Return to guides](https://magolol.github.io)

