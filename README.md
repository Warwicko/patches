# patches

innocent patches for the switch for using certain homebrews~like Tinfoil, see this FAQ if you get a red screen when using the hekate patches: https://rentry.org/SwitchFAQ

## how to patches

hello! welcome to patches. you need to download and extract the appropriate zip file from the [releases page](https://github.com/ITotalJustice/patches/releases) to the root (highest directory) of your sd card! this should merge the `/atmosphere/` folder in the zip with the atmosphere folder on your sd card! you should not have an `/atmosphere/atmosphere/` folder, nor should you have an `/sd/`, `/fusee/`, or `/hekate/` folder on your sd. 

## atmosphere patches

if you start your [Atmosphere CFW](https://github.com/Atmosphere-NX/Atmosphere) by injecting the corresponding `fusee-primary.bin` RCM payload from whichever Atmosphere release you are using, you can simply use the [fusee.zip](https://github.com/ITotalJustice/patches/releases/latest/download/fusee.zip)

## hekate patches (ez mode)

if you start your CFW using hekate, you should evaluate how you are launching CFW before trying to patches. an easy way to launch CFW using hekate that is compatible with all homebrew apps is to just use hekate to launch fusee-primary! you can just use the same fusee patches, you don't need the special files further below. if you accidentally grabbed the special `hekate.zip` file in the [releases pages](https://github.com/ITotalJustice/patches/releases), that is ok! you can boot with fusee-primary using the `hekate.zip`, you just can't boot using the fss0 mode below using the `fusee.zip`. i tried to make it easy and foolproof unless you are using the hacker method in the next section. When I use hekate I just have a one line config entry to boot Atmosphere, after copying my latest `fusee-primary.bin` into the `/bootloader/paylods/` folder. 

```ini
[Atmosphere CFW]
payload=bootloader/payloads/fusee-primary.bin
```

here is a helpful guide on how to launch fusee-primary using hekate and no need for special patches and configs, see step 3 in Erista guides: 
* Unpatched Erista (v1 Switch) using emunand: https://rentry.org/EristaEmuNAND
* Unpatched Erista (v1 Switch) using sysnand: https://rentry.org/EristaSysNAND
* Step 2 of the Mariko emunand guide: https://rentry.org/MarikoEmuNAND
* Migration info in the Mariko sysnand guide: https://rentry.org/AtmosphereSysNAND

## hekate patches (fss0 hard mode)

hello, i do not boot this way, you are probably some kind of a hacker if you are launching with special hekate configs. the important thing to know is that you need to actually grab the special [hekate.zip](https://github.com/ITotalJustice/patches/releases/latest/download/hekate.zip) and add some special hacking line `kip1patch=nosigchk` into your `hekate_ipl.ini` config file:

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

congrats!! you now have patches~

----

## sources

Usual sources are:

[GBAtemp](https://gbatemp.net)

[HarukoNX](https://github.com/HarukoNX)

i do not do anything with creating patches, this is just some helpful information for educational purposes. ask a homebrew hacker if you need help patching but remember to always respect all intellectual property rights and all local/international laws. 
