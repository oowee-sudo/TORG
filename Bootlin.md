
### U-boot
- Compilation :
```
$ export PATH=/path/to/toolchain/bin:$PATH
$ make am335x_evm_defconfig
$ make DEVICE_TREE=am335x-boneblack-wireless CROSS_COMPILE=arm-linux- 
```
- Environment commands
**`printenv <variable-name>`** 
**`setenv <variable-name> <variable-value>`** : Changes or defines a new variable,  in RAM
**`editenv <variable-name>`**  Interactively edits the value ,  in RAM
**`saveenv`** : Saves the current state of the environment to storage for persistence.
`bootcmd`: list of commands executed automatically by U-Boot after the count down
`bootargs`: Linux kernel command line
- Memory manipulation 
Addresses manipulated in U-Boot are directly physical addresses
**`md [.b, .w, .l, .q] address [# of objects]`** : Memory display
**`mw [.b, .w, .l, .q] address value [count]`** : Memory write
**`mm [.b, .w, .l, .q] address`** : Memory modify (modify memory contents interactively starting from address)
- NAND flash
**`nand info`** 
**`nand read <addr> <off|partition> <size>`** (from nand to ram)
**`nand erase [<off> [<size>]]`** 
**`nand write <addr> <off|partition> <size>`** 
- MMC 
**`mmc info`** 
**`mmc read <addr> <blk#> <cnt>`** (from blk to ram)
**`mmc write <addr> <blk#> <cnt>`** 
**`mmc part`** : to show partition table
**`mmc dev`** : to show/set current MMC device
- USB storage
**`usb info`**
**`usb read <addr> <blk#> <cnt>`**
**`usb write <addr> <blk#> <cnt>`**
**`usb part`**
**`usb dev`**
### Kernel
**`make -j 8`** : use multi threading
**`export CROSS_COMPILE="ccache arm-linux-"`** To recompile faster : ccache compiler cache
**`make INSTALL_MOD_PATH=<dir>/ modules_install`** : install modules in path (other that the host )
Modules utils: **`lsmod`** **`modinfo`** **`insmod`** **`rmmod`** **`modprobe`** 