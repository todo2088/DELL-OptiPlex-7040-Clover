# DELL-OptiPlex-7040-Clover
Clover for DELL OptiPlex 7040 with Skylake CPU & GPU

Only fix the Graphics by Bios hack, Ethernet, USB, and sound card with AppleALC, but, is enough! Less is more.

Test with DELL OptiPlex 7040 which using i5-6500, Intel HD Graphics 530, Intel I219LM2 Ethernet, macOS 10.14.

- I extract the BIOS.rom by AMI Flasher utility.
- I modity the DVMT to 64MB by [https://www.firewolf.science/2015/04/guide-intel-hd-graphics-5500-on-os-x-yosemite-10-10-3/]
- DVMT Pre-Allocated address is 0x350, so "setup_var 0x350 0x2" to set 64MB [中文教程](https://zhuanlan.zhihu.com/p/39798235)
- Note: the DVMT fixup will lose after set BOIS to factory default!

If you don't want to fix the BIOS, you can just using the WhateverGreen hotpatch by just using CLOVER, see this branch [https://github.com/irelandKen/DELL-OptiPlex-7040-Clover/tree/macOS_10.14.2_WhateverGreen] 


## DVMT fix step
1. unzip 'EFI-shell.zip' to a `FAT32` partition of a USB disk
   
   you will see some thing like this : "/Volumes/UDISK/EFI/BOOT/bootx64.efi" 
   
   or "E:/EFI/BOOT/bootx64.efi" 
2. reboot you machine using this this USB disk in `UEFI BOOT MODE`
   
   and you will see a cmd line
3. just run `setup_var 0x350 0x2` using this cmd line

4. fine, the graphics is ok to boot up macOS

### Know issue 
1. Just one DP port work
   
   you need to switch to an other DP port and reboot, if no DP signal after you see the "white apple" startup logo.
