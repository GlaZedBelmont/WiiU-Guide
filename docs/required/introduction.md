# Introduction

## Prerequisite

> [!NOTE]
> First of all, please make sure that you have all the necessary equipment.
>
> - An SD card
> - An internet connection (but if you're here it means you have one).
> - A WiiU in 5.5.4 (you can upgrade, the exploit is very stable)
> - A device with an SD card reader, such as a computer.

> [!WARNING]
> Your SD card must have enough space, if you hesitate you can read this [guide](choose-sd-card.md).<br />
> Some hacking requires a large storage capacity!

If you have everything you need and have read the entire home page, then **let's go!**

## Preparing the SD card

First of all, you need to insert your SD card into your computer and format it in **FAT32** and especially not in **exFAT**.
If your SD card is larger than 32 GB, you may need software such as **fat32 format**.

## Installation of the Homebrew Launcher

Before you can install it you need to download the [`homebrew_launcher.v1.4.zip`](https://github.com/dimok789/homebrew_launcher/releases/download/1.4/homebrew_launcher.v1.4.zip) file.<br />
You will also need the file named [`payload.elf`](https://github.com/wiiu-env/homebrew_launcher_installer/releases/download/v1.4/payload.zip).

1. Extract the `homebrew_launcher.v1.4.zip` archive to the root of your SD card.
2. Extract the `payload.zip` archive into the `wiiu` directory.

You now have the homebrew launcher on your SD card. <br>
But as it is, it is not very useful because the Homebrew Launcher requires applications. 

So we will install an application.

## Homebrew App Store

As its name suggests, this application is an application store. <br>
It allows you to download huge amounts of applications directly from your wiiu without having to turn it off and remove the SD card.

You can download it by [clicking here](https://github.com/vgmoose/hb-appstore/releases/download/2.2/wiiu-extracttosd.zip).<br>
The zip archive should be called `wiiu-extracttosd.zip`.

Extract the file `wiiu-extracttosd.zip` from the root of your SD card. <br>
If you are asked to merge the file, click **yes** or **merge**.

## Checking files

This step is not necessary but can be useful to make sure you have all the necessary files to launch the Homebrew Launcher.

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

If in the `appstore` folder on your SD card, you have a file named `hbas.elf`, you can delete it, it is not useful if you are using the rpx version (which is the case).

## Launch of the Homebrew Launcher

We can now launch the Homebrew Launcher.<br>
To do so, simply follow these steps.

1. If your console is on, turn it off.
2. Insert your SD card into the port on your wiiu.
3. Turn on your wiiu.
4. Launch the console's web browser.
5. Navigate to `wiiuexploit.xyz` or `u.wiidb.de`.
6. Click on the button `Run Homebrew Launcher` or `Haxx`.
7. A blank page should load, wait a few seconds. If nothing happens, or your lower left mii doesn't move at all, then turn off your console. Otherwise congratulations, you have just launched the Homebrew Launcher.

## Error management

<!-- tabs:start -->

#### ** The Browser Crashed **

This can happen, just try again. Also clear your browser settings, set `u.wiidb.de` or `wiiuexploit.xyz` as a bookmark, close the browser and reopen it again. Don't do too much other stuff in the browser or it won't work!

#### ** FSGetMountSource **

Format your SD card in FAT32.

#### ** FSOpenFile **

You are missing the payload.elf file.

<!-- tabs:end -->

[Source of errors](https://gbatemp.net/threads/more-stable-webhack-for-5-5-2-5-5-3-5-5-4-released.528757/)

## Finish

If everything worked then congratulations you have a working installation of the Homebrew Launcher on SD card.
<hr>

#### [➡️ Choose CFW](choose-cfw.md) {docsify-ignore}