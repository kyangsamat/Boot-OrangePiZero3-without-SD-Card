**OrangePiZero 3 Boot without Micro SD Card**

*This only works on the official images Ubuntu and Debian of the Orange Pi Zero 3

Enter the FEL mode and flash the U-Boot to the SPI. 

On a Linux Computer

Download the fel-sdboot.sunxi file and write the "magic binary" to the SD Card using balenaEtcher or recording on SD Card using the command

`sudo dd if=fel-sdboot.sunxi of=/dev/sdb bs=1k seek=8`

Output :

`8+0 records received`

`8+0 records sent`

`8192 bytes (8.2 kB, 8.0 KiB) copied, 0.0585641 s, 140 kB/s`

Download the [Sunxi-tools](https://linux-sunxi.org/Sunxi-tools) from <https://linux-sunxi.org/Sunxi-tools> Usually it shipped with the package of Linux

Download the u-boot-sunxi-with-spl.bin to the computer

Then insert the SD Card into the Orange Pi Zero 3 and connect it to a computer using the USB-C (USB0) of the Orange Pi Zero 3 and run `sudo sunxi-fel version` in the terminal. It should give a return if the Orange Pi Zero 3 is detected and in FEL mode.

Run `sunxi-fel -v -p spiflash-write 0 u-boot-sunxi-with-spl.bin` command to write the u-boot. 

It shoud return with `100% [=============================] 828 kB, 69.6 kB/s` when it’s done.

Now the Orange Pi Zero 3 is ready for booting without a SD Card inserted. It can boot from the USB ports or Network.

Inspired from https://4pda.to/forum/index.php?showtopic=1073025&st=700\#entry127597333
