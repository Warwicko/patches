# Signature Patches
Signature patches are created to be used alongside Atmosphere for loading homebrew from the home menu. If you need assistance setting up Atmosphere, the recommended guide is https://rentry.org/SwitchHackingIsEasy

Atmosphere 1.0.0 renamed many important files, see https://rentry.org/MigrateToAtmosphere1_0_0 for assistance with migrating from previous Atmosphere versions. 

## How to install Signature Patches

1. [Download the latest release.](https://github.com/ITotalJustice/patches/releases/latest)
    * Read the release page to ensure your version of Atmosphere is supported!

2. Unzip the release into the root of your SD card. 
    * Make sure to click **yes** for overwriting any files and merging folders.
    * Make sure the `/atmosphere/` folder in the zip merges with the atmosphere folder on your SD card! You should not have an `/atmosphere/atmosphere/` folder, nor should you have an `/sd/`, or `/SigPatches/` folder on your SD card. 

3. Boot into atmosphere. You should now be using signature patches.


## Hekate Patches (EZ Mode)

If you wish to start your CFW with Hekate, we highly suggest chainloading fusee. This is the best method to boot Atmosphere without directly pushing fusee.bin.

To chainload atmosphere place the [latest fusee.bin](https://github.com/Atmosphere-NX/Atmosphere/releases/latest/download/fusee.bin) in `/bootloader/payloads/` then edit your hekate_ipl.ini to contain the following,
```ini
[Atmosphere CFW]
payload=bootloader/payloads/fusee.bin
```


## Hekate Patches (fss0 Hard Mode)

I do not boot this way, and I suggest you don't either. Make sure that you edit your hekate_ipl.ini to contain `kip1patch=nosigchk`. Like this:

```ini
[CFW - FSS0 SYS]
fss0=atmosphere/package3
kip1patch=nosigchk
emummc_force_disable=1

[CFW - FSS0 EMU]
fss0=atmosphere/package3
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
