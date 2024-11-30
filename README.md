# Cyberdev's Bootanimation Installer Script!

## What is this?
This script is designed to install any bootanimation to /product/media directly via adb.

Giving the end user complete customization of what kind of bootanimation they want to see on boot, however this is NOT systemless and it will overwrite any current installed bootanimation, updates to custom ROMS and Stock ROMS will always overwrite the bootanimation.


## How does it work?
This script works like a gapps package, but in a way not exactly like a gapps package normally would work, when you send over the package via adb to your custom recovery will recognize it as a gapps package this was done this way because the /product partition is set to read-only so nothing can be written unless your system is preset to r/w, this will temporarily set /product to r/w and install your bootanimation then set it back to read-only or whatever it was before being set to r/w stock usually sets it to Read-Only.

However this script will not remove anything or any other gapps package you installed previously so you do not need to worry about interfering with a current or previous gapps installation, your install of gapps is safe!


## How do i install a bootanimtion?
To install a bootanimation find a bootanimation you want to use, we suggest using bootanimations that have is a set for example:

- bootanimation-dark.zip
- bootanimation.zip

This is recommended because most devices have these two files anyways, the difference between both is both are the same animation but bootanimation.zip is the light version and the bootanimation-dark.zip is the dark version for the boot animation.

You can change one or both but it would make no sense to have two different ones it would make things confusing and not worth it.

Now extract the script and in that folder just place your files in "/system/product/media" then go back to the root of the script and compress all 5 files back into a zip and then reboot into your custom recovery and choose. apply update over adb.

Then on your PC send over the package via adb by using this command

`.\adb -d sideload filename.zip`

This shouldn't take long.

now if you're flashing a new rom, before flashing this package, install your desired gapps package first then then reboot into recovery again and then flash this package before rebooting into your OS.

This should work on devices that has not done a clean install but we do suggest it if possible!

## What are the requirements to use this script?
- Custom Recovery
- Android 15 SDK35
- Arm64-v8a device
- Unlocked bootloader (can be relocked on stock firmwares)

# WARNING:
Backup any current bootanimations before flashing this script they cannot be recovered once you do this, only way to get it back is either via a system update or OS reflash you have been warned, i am not responsible for any damages to your device from using thus script or loss of your stock bootanimations that you didn't backup!



