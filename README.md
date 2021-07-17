
# Patches

Innocent patches for the switch for using certain homebrews like Tinfoil, see this FAQ if you get a red screen when using the Hekate patches: https://rentry.org/SwitchFAQ

## How to use patches

Hello! Welcome to use these patches you need to download and extract the appropriate zip file from [releases page](https://github.com/ITotalJustice/patches/releases) to the root (highest directory) of your SD card! This should merge the `/atmosphere/` folder in the zip with the atmosphere folder on your SD card! You should not have an `/atmosphere/atmosphere/` folder, nor should you have an `/sd/`, `/fusee/`, or `/hekate/` folder on your SD card. 

## Atmosphere Patches

If you start your [Atmosphere CFW](https://github.com/Atmosphere-NX/Atmosphere) by injecting the corresponding `fusee-primary.bin` RCM payload from whichever Atmosphere release you are using, you can simply use the [fusee.zip](https://github.com/ITotalJustice/patches/releases/latest/download/fusee.zip)

## Hekate Patches (EZ Mode)

If you start your CFW using Hekate, you should evaluate how you are launching CFW before trying to patches. an easy way to launch CFW using Hekate that is compatible with all homebrew apps is to just use Hekate to launch fusee-primary! You can just use the same fusee patches, you don't need the special files further below. if you accidentally grabbed the special `hekate.zip` file in the [releases pages](https://github.com/ITotalJustice/patches/releases), that is ok! you can boot with fusee-primary using the `hekate.zip`, you just can't boot using the fss0 mode below using the `fusee.zip`. I tried to make it easy and foolproof unless you are using the hacker method in the next section. When I use Hekate I just have a one line config entry to boot Atmosphere, after copying my latest `fusee-primary.bin` into the `/bootloader/payloads/` folder. 

```ini
[Atmosphere CFW]
payload=bootloader/payloads/fusee-primary.bin
```

Here is a helpful guide on how to launch fusee-primary using Hekate and no need for special patches and configs, see Step 3 in Erista guides: 
* Step 3 of the Unpatched Erista (v1 Switch) EmuNAND guide: https://rentry.org/EristaEmuNAND
* Step 3 of the Unpatched Erista (v1 Switch) SysNAND guide: https://rentry.org/EristaSysNAND
* Step 2 of the Mariko EmuNAND guide: https://rentry.org/MarikoEmuNAND
* Migration info in the Mariko SysNAND guide: https://rentry.org/AtmosphereSysNAND

## Hekate Patches (fss0 Hard Mode)

I do not boot this way, you are probably some kind of a hacker if you are launching with special hekate configs. the important thing to know is that you need to actually grab the special [hekate.zip](https://github.com/ITotalJustice/patches/releases/latest/download/hekate.zip) and add some special hacking line `kip1patch=nosigchk` into your `hekate_ipl.ini` config file:

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

Congrats!! You now have patches~

----

## Sources

Usual sources are:

[GBAtemp](https://gbatemp.net)

[Google](https://google.com)

I do not create patches, this is just some helpful information for educational purposes. Ask a homebrew hacker if you need help patching but remember to always respect all intellectual property rights and all local/international laws. 
