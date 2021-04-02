Free Wipe for Windows
=====================
Information:
-------------
WIKI
https://github.com/howser2016/freewipeforwin1/wiki
COMPILED VERSION
https://drive.google.com/file/d/1-hWH_wX4BQrqBUMapjeFvc5HKhO1bADj/view?usp=sharing

The easiest way to wipe a Windows computer, no need for technical skills, USB or CD or DVD. Just install the software and restart the computer. 
It will try to wipe all storage plugged in the computer at the time of the wipe.  
It has three wipe options which are presented after you have installed and have restarted the computer.

WARNING: Used entirely at your own risk. NO WARRANTIES IMPLIED OR GIVEN. 

WARNING: Has NOT been tested beyond Windows 7, and will NOT work on UEFI boot configurations. 

How to Build:
-------------
First you need to install InnoSetup. It's included in this repo.
You can then use it to open the file `installer` and simply hit build.


How to customize:
-----------------
The project uses a light weight Linux distribution. It's is in a compressed file in Downloads area of the wiki `lupu_528.sfs`.
First thing you need to do is extract it. On linux you can install `squashfs-tools-ng` and issue the following commands:

```
# Convert squashfs to tar
sqfs2tar lupu_528.sfs > lupu_528.tar
# Extract tar archive
mkdir linux
tar -xpf lupu_528.tar -C linux
# make your changes in the linux directory
# Recreate it.
tar -cpf lupu_528.tar -C linux '.'
# Convert back to squashfs
tar2sqfs -c gzip lupu_528.sfs < lupu_528.tar
```

Once you have produced the sfs file, you can then rebuild the project as usual.
