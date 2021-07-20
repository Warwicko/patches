# Signature Patches
Signature patches are created to be used alongside Atmosphere for loading certain homebrew from the home menu.

## How to install Signature Patches

1. [Download](https://github.com/ITotalJustice/patches/releases/latest) the latest release.
    * If you use `fusee-primary.bin` to boot into atmosphere, download `fusee.zip`.
    * If you use `fusee-secondary.bin` to boot into atmosphere, download `hekate.zip`.
    * If you're unsure on which release to get then check your `hekate_ipl.ini` file located in your `/bootloader/` folder.
        * If you have no such file, then get the `fusee.zip` release.
        * If you see the following line `payload=bootloader/payloads/fusee-primary.bin` in your `hekate_ipl.ini` file, download `fusee.zip`.
        * If you see the following line `fss0=atmosphere/fusee-secondary.bin` in your `hekate_ipl.ini` file, download `hekate.zip`.
2. Unzip the release you've chosen into the root of your SD card. 
    * Make sure to click **yes** for overwriting any files and merging folders.
    * Make sure the `/atmosphere/` folder in the zip merges with the atmosphere folder on your SD card! You should not have an `/atmosphere/atmosphere/` folder, nor should you have an `/sd/`, `/fusee/`, or `/hekate/` folder on your SD card. 

3. Boot into atmosphere. You should now be using signature patches.


## Hekate Patches (EZ Mode)

If you wish to start your CFW with Hekate, we highly suggest chainloading fusee-primary. This is the best method to boot Atmosphere without directly pushing fusee-primary.bin.

To chainload atmosphere place the [latest fusee-primary.bin](https://github.com/Atmosphere-NX/Atmosphere/releases/latest/download/fusee-primary.bin) in `/bootloader/payloads/` then edit your hekate_ipl.ini to contain the following,
```ini
[Atmosphere CFW]
payload=bootloader/payloads/fusee-primary.bin
```


## Hekate Patches (fss0 Hard Mode)

I do not boot this way, and I suggest you don't either. The important thing to know about this method is that you need to grab the special [hekate.zip](https://github.com/ITotalJustice/patches/releases/latest/download/hekate.zip) and then edit your hekate_ipl.ini to contain `kip1patch=nosigchk`. Like this:

```ini
[CFW - FSS0 SYS]
fss0=atmosphere/fusee-secondary.bin
kip1patch=nosigchk
emummc_force_disable=1

[CFW - FSS0 EMU]
fss0=atmosphere/fusee-secondary.bin
kip1patch=nosigchk
emummcforce=1
```



----

## Sources

Usual sources are:

[GBAtemp](https://gbatemp.net)

[Google](https://google.com)

----
*Repo is mostly automated.*

**This is just for educational purposes. Ask a homebrew developer if you need help with signature patches and remember to always respect all intellectual property rights and all local/international laws!**