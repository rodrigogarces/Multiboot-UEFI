##### Table of contents
1. [Introduction](#introduction)
2. [Installation](#installation)
3. [ISO conversion](#iso-conversion)
4. [Adding a ISO to thumbdrive](#adding-a-iso-to-thumbdrive)
5. [UEFI boot](#uefi-boot)

##### Introduction
This tutorial is a simplified version (with pictures) of the only functional way that i found to make a multiboot uefi thumdrive.
Is based on [easy2boot](http://www.easy2boot.com/), that is a free multiboot tool, and offers support to multiboot.
This tutorial is based on windows version, because only windows version have graphical interface, and is easy to work.

##### Installation
* Download latest version from official [easy2boot website](http://www.easy2boot.com/download) (at time i write this is [v 1.99](http://files.easy2boot.com/200003273-a94b8ab584/Easy2Boot_v1.99.exe)) and install on your computer.
* Connect your thumb driver and certified that is correctly indentified by windows. (PIC)
* Open easy2boot as administrator (PIC) and secet your thumb drive. Be carefull to not select the wrong drive, and make shure you double checked drive, because *all your data stored on the drive will be erased*
* Click the red button "make E2B drive" and wait. E2B will automatically copy all necessary data to tur your drive in a bootable drive.

##### ISO conversion
* In order to use multiboot on UEFI, you need to convert OS images from ISO to a image partition (.imgPTN). for this you will need [mpi pack](http://www.easy2boot.com/download/mpi-pack/). Download and unzip
* Open unzipped folder and install imDisk (imDisk/imdiskint.exe)
* Double click "CreateDesktopShortcuts.cmd" to create three shortcuts on desktop (MakePartImage, MPI_FAT32 and MPI_NTFS), will be very usefull to convert images.
* Drag an ISO file to MPI_FAT32 and follow on screen instructions to convert to a partition image file (.imgPTN).
If sucess, terminal background will turn green.

**Hint:** The partition image file will be created on same folder that original image (ISO) file.

##### Adding a ISO to thumbdrive
* Copy partition image created on previous step to your thumb drive, on correct folder (if is linux, to linux folder, if windows, to windows specific version forder). Its not mandatory, but mantains organization and easy to manage installed images. :)
You can add many images as you want. The only limitaion is your driver capacity.
* After add a partition image file, run "MAKE_THIS_DRIVE_CONTIGUOUS.cmd" to ensure that all file are contiguous on drive. (If a partition image is not contiguous, will not boot)(And yes, you need to run this each time you add a  partition image).
**Pro tip:** If you want to use a secondary partition, make a second partition **before add the first** partition image and run "MAKE_THIS_DRIVE_CONTIGUOUS.cmd". this will ensure that your partition images won't corrupt. 

##### UEFI boot
(Explanations and limitations)
You will need a litlle hackish method to multiboot tunder uefi.
I don't know why, but seems that uefi doesn't support multiboot natively (?). It's nonsesnse, considering that bios (legacy) mode can do this like a charm.
On uefi, you need to shitch partirions, to obtain only **one** uefi bootable partition.
Due to this limitation, you will need a little extra step.

Mount uefi iso if you have acess to bios (legacy) mode


* Boot your thumb drive via bios (legacy) mode.
* Select iso you want to boot.
* prompt yes. (This will replace your thum drive partition with iso partition image that you select)
* Press f9 to reboot machine and boot your thumb drive on uefi mode

To unmount iso uefi image
* Restart your pc on bios mode
* Press 0 and enter to return to easy2boot menu

Mount uefi iso if you don't have acess to bios (legacy mode)

Windows tutorial...
TODO
