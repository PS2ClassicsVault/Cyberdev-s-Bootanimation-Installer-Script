# Cyberdev's Bootanimation Installer Script!

## What is this?
This script is designed to install any bootanimation to /product/media directly via adb.

Giving the end user complete customization of what kind of bootanimation they want to see on boot, however this is NOT systemless and it will overwrite any current installed bootanimation, updates to custom ROMS and Stock ROMS will always overwrite the bootanimation.


## How does it work?
This script works like a gapps package, but in a way not exactly like a gapps package normally would work, when you send over the package via adb to your custom recovery will recognize it as a gapps package this was done this way because the /product partition is set to read-only so nothing can be written unless your system is preset to r/w, this will temporarily set /product to r/w and install your bootanimation then set it back to read-only or whatever it was before being set to r/w stock usually sets it to Read-Only.

However this script will not remove anything or any other gapps package you installed previously so you do not need to worry about interfering with a current or previous gapps installation, your install of gapps is safe!


## How do i install a bootanimation?
To install a bootanimation find a bootanimation you want to use, we suggest using bootanimations that have is a set for example:

- `bootanimation-dark.zip`
- `bootanimation.zip`

This is recommended because most devices have these two files anyways, the difference between both is both are the same animation but bootanimation.zip is the light version and the bootanimation-dark.zip is the dark version for the boot animation.

You can change one or both but it would make no sense to have two different ones it would make things confusing and not worth it.

Now extract the script and in that folder just place your files in `/system/product/media` then go back to the root of the script and compress all 5 files back into a zip and then reboot into your custom recovery and choose. apply update over adb.

Then on your PC send over the package via adb by using this command

`.\adb -d sideload filename.zip`

This shouldn't take long.

now if you're flashing a new rom, before flashing this package, install your desired gapps package first then then reboot into recovery again and then flash this package before rebooting into your OS.

This should work on devices that has not done a clean install but we do suggest it if possible!

## What are the requirements to use this script?
- Custom Recovery
- Arm64-v8a device
- Unlocked bootloader (can be relocked on stock firmwares)

There are 5 versions for different versions of android, if your looking to see if your android version is supported please look in the [releases](https://github.com/PS2ClassicsVault/Cyberdev-s-Bootanimation-Installer-Script/releases) section of this repository to see if your android version is supported

# FAQ

## Is this hardware dependent or OS dependent?
- This is OS dependent as it requires a specific version of android you need to have installed for the version of the installer your trying to use to function or even proceed with the installation, however the only limitations this script has is that it only supports arm64-v8a devices, not armeabi-v7a devices!

## Can i request script support for other versions of android beyond what is currently available in this repository?
- No, that unfortunately would take a lot of my time that i frankly do not have these days.

## How do i backup my current bootanimation?
- I recommend using a file manager that can access the root of your device easily to backup your files, they are usally in this directory

`/product/media`

if your using one of our special scripts they will install your files to this directory instead:

`/system/media`

## Do i need any software on my pc to use adb/fastboot?
- Yes, you will need platform-tools to use adb we recommend downloading it from [here](https://technastic.com/android-sdk-platform-tools-download/) extract it and then put our script in the platform-tools and then open a terminal that leads to that directory of the platform-tools folder and then run the command we mention ealier in this readme to flash our script!

It is also recommended that you have installed the device drivers from your manufacturers website if they are available or required by your device for your PC to be reconized by adb.

## Does this script come with it's own bootanimation or do i need to provide my own?
- This script does not include any bootanimation you must provide that on your own, you can do that by extracting the script and placing the bootanimation into the following folder within the script `/system/product/media` then recompress the script and then run the command to flash the script via adb.

## I'm receving an error when installing the script saying "Not enough space for bootanimation...Aborted!" What can i do?
- This is happening because you installed a certain gapps package that used most of the capacity of the devices partition required for this script to install to.

However, we recommend to install smaller size gapps package like MindTheGapps his/her gapps is small and perfect.

If you're still getting this error pleaee report them please.

# Additional Information:

## WARNING:
Backup any current bootanimations before flashing this script they cannot be recovered once you do this, only way to get it back is either via a system update or OS reflash you have been warned, i am not responsible for any damages to your device from using this script or loss of your stock bootanimations that you didn't backup!



