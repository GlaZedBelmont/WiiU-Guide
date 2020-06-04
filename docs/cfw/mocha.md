# Mocha CFW

`MochaCFW` is a **Custom Firmware** developed by `dimok789`.<br>
It's called **«free»** because it doesn't require a DS Virtual Game.<br>
Its only small flaw is that it has to be launched from the web browser and must be restarted each time the console is rebooted.

## Exploit

If you followed the tutorial correctly, you should have a Homebrew Launcher working.<br>
Now you have to choose what type of exploit you want to use.

- #### Online Exploit {docsify-ignore}

> [!WARNING]
> Requires an Internet connection every time you want to launch the Homebrew Launcher.

For more information on `Online Exploit`, you can [read our guide](online-exploit.md) on this subject.

- #### Indexiine {docsify-ignore}

> [!WARNING]
> Requires modifying system files.<br>
> Requires an internet connection to set up the exploit.

For more information on `Indexiine`, you can [read our guide](indexiine.md) on this subject.

## SD Preparation

If you followed the introduction, you must have already launched the Homebrew Launcher.<br>
But here's a little reminder.

You must have the following files:
- sd:/
    - wiiu
        - payload.elf
        - apps/
            - homebrew_launcher/
                - homebrew_launcher.elf
                - meta.xml
                - icon.png
            - appstore/
                - appstore.rpx
                - meta.xml
                - icon.png

So we're going to add MochaCFW.<br>
You can download it [here](https://www.wiiubru.com/appstore/zips/mocha.zip).

Then simply extract the archive to the root of your SD card.<br>
So you must have as files on your SD card:
- sd:/
    - wiiu
        - payload.elf
        - apps/
            - homebrew_launcher/
                - homebrew_launcher.elf
                - meta.xml
                - icon.png
            - appstore/
                - appstore.rpx
                - meta.xml
                - icon.png
            - mocha
                - mocha.elf
                - meta.xml
                - icon.png

## Customized launch image

If you have a custom launch image you can run it with MochaCFW if you place it in this folder:

```
sd:/ > wiiu > apps > mocha > launch_image.tga
sd:/wiiu/apps/mocha/launch_image.tga
```

## Autoboot

> [!NOTE]
> The autoboot of MochaCFW just avoids the Mocha menu when launching the application.

Once this option is enabled, a file will be created with the name `config.ini' and placed in the `sd:/wiiu/apps/mocha/` directory.

You can open the file with a simple text editor.<br>
It's going to give a result like this:
```
[MOCHA]
viewMode=0
directLaunch=1
launchImage=1
noIosReload=0
launchSysMenu=1
redNAND=0
seeprom_red=0
otp_red=0
syshaxXml=0
```

## Backup the NAND

- #### **What is the purpose of a NAND backup?** {docsify-ignore}

This can help unlock your WiiU if something has gone wrong. That's why nand backups are highly recommended.

- #### **Instructions** {docsify-ignore}

> [!NOTE]
> The NAND of your system can do either 8 GB or 32 GB (depending on the model). So your SD card must be larger. To know the capacity of your WiiU simply look at its color:
> - If the color is white then your console is 8 GB.
> - If the color is black then your console is 32 GB.
> 
> If your SD card does not have sufficient capacity, you can skip the MLC section.<br>
> The MLC section contains backup files and game data.<br>
> The MLC section is not required to recover most bricks.

> [!WARNING]
> Restoring a NAND backup **requires micro-soldering skills** and **additional hardware**.<br>
> **HOWEVER**, a NAND backup is **always useful**, so don't neglect it!<br>
> Your NAND backup is **unique** to your system. **Backups from other consoles will not work**.

To be able to copy your NAND, it will take several hours depending on the capacity of the console and requires an additional software: `Wii U NAND Dumper`. You can download it [here](https://www.wiiubru.com/appstore/zips/nanddumper.zip).

1. Extract the zip archive to the root of your SD card.
2. Plug your SD card into your WiiU and turn it on.
3. Launch the `Homebrew Launcher`.
4. Launch `MochaCFW`.
5. This will redirect you to the home menu, you just have to restart the exploit to go back to the home menu.
6. Launch `Wii U NAND Dumper`.
7. A configuration menu will appear, here is the recommended configuration:
   - Dump SLC: **yes**
   - Dump SLCCMPT: **yes**
   - Dump MLC: **optional**
   - Dump OTP: **yes**
   - Dump SEEPROM: **yes**
8. Press A to start the dump process. 
**The process will take time!**<br>

9. Once the dump process is complete, turn off your console then remove your SD card and plug it into your computer.
10. To make sure you don’t lose the files, copy the slc.bin, slccmpt.bin, seeprom.bin, otp.bin and if you chose to go with a full backup, every mlc.bin.part file to your computer.
11. Delete the files from your SD Card to free up space.

## MochaCFW and its alternatives
MochaCFW alternatives are not real alternatives. They are modified versions adding other hacks. <br>
Here is the list of modified versions:
- MochaCFW + FSHax
- MochaCFW FAT32
- MochaCFW SD

#### **MochaCFW + FSHax** {docsify-ignore}

This modified version adds the `FSHax`. This modified version was designed to be able to execute hacks like `FTPiiu`.

#### **MochaCFW FAT32** {docsify-ignore}

MochaCFW FAT32 is used to add the possibility to use USB devices formatted in FAT32.

#### **MochaCFW SD** {docsify-ignore}

MochaCFW SD allows a certain application to access the SD card. This is useful for `TCPGecko` or even `SDGeckiine`.

## Mocha Payload

> [!NOTE]
> Mocha Payload is a modified version of the `payload.elf` file.<br>
> It was developed by Vincent-Coding (i.e. the creator of this guide 😉)<br>
> This program is based on `GaryOderNichts'` code.

They allow to launch `MochaCFW` directly, instead of `Homebrew Launcher`.<br>
This means that the `Homebrew Launcher` is inaccessible through the web browser. Therefore, you need to have the `Homebrew Launcher Channel` installed.

> [!NOTE]
> If you decide to run MochaCFW twice, you have a chance to crash your console. Otherwise it will redirect you to the Mii Editor.

> [!WARNING]
> You must absolutely place MochaCFW in the following folder:
> ```
> sd:/ > wiiu > apps > mocha
> sd:/wiiu/apps/mocha/
> ```
> And the payload.elf file must be here:
> ```
> sd:/ > wiiu > payload.elf
> sd:/wiiu/payload.elf
> ```