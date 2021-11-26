**There exist two emuMMC types. One exists as a hidden partition, the other exists as SD files.

**Pros and Cons to partition based**

-Least chance for corruption

-Migrating to a new SD is a pain in the ass

-You must format the sd in order to create one

**Pros and Cons to file based**

-Easy to transfer

-Does not require for the user to format the SD

-More prone to corruption

-Transferring games between your SD card and your emuMMC via system settings is not possible. This is due to an unfixed bug.

**Creating partition based emuMMC**

If you aren't already booted into hekate, please do so now. 

Select the `Tools` tab -> `Partition SD Card` -> `Ok`

**Please note that starting the partition process will delete all data on the SD. It might've deleted `boot.dat`, `boot.ini`, and `payload.bin` (if applicable.) Please re-add these missing files once finished.**

Move the `emuMMC RAW` slider until it says `29 full`. Then press start.

Once the process is complete, return to the `Home` tab -> `emuMMC`. Then select create emuMMC. Select SD partition. Wait for the process to complete.

You can make sure the emuMMC is enabled by checking the `emuMMC` tab.

**Creating file based emuMMC**

If you aren't already booted into hekate, please do so now. 

Select the tab labeled `emuMMC`. Then select create emuMMC. Select SD files. Wait for the process to complete.

You can make sure the emuMMC is enabled by checking the `emuMMC` tab.






**[Return to main page](https://magolol.github.io)**

**[Return to guides](https://magolol.github.io)**