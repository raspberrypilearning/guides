# How to get and install NOOBS

To get started with Raspberry Pi you need an operating system. NOOBS (New Out Of the Box Software) is an easy operating system install manager for the Raspberry Pi.

## Buy a preinstalled SD Card

The easiest way to get NOOBS is to buy an SD card with NOOBS already installed, available at the [Swag Store](http://swag.raspberrypi.org/products/noobs-8gb-sd-card). Alternatively, if you have an SD card (8GB recommended), then you can download NOOBS for free and install it on your card.

## Download

1. Using a computer with an SD card reader, visit the offical Raspberry Pi [Downloads page](http://www.raspberrypi.org/downloads/).
1. Click on the Download ZIP button under ‘NOOBS (offline and network install)’, and select a folder to save it to.
1. Extract the files from the zip.

## Format your SD Card

It is best to format your SD card before copying the NOOBS files onto it. To do this:

1. Visit the [SD Association’s website](http://www.sdcard.org/) and download [SD Formatter 4.0](https://www.sdcard.org/downloads/formatter_4/index.html) for either Windows or Mac.
1. Follow the instructions to install the software.
1. Insert your SD card into the computer or laptop’s SD card reader and make a note of the drive letter allocated to it, e.g. `G:/`
1. In SD Formatter, select the drive letter for your SD card and format it.

## Drag and drop NOOBS files

1. Once your SD card has been formatted, drag all the files in the extracted NOOBS folder and drop them onto the SD card drive.
1. The necessary files will then be transferred to your SD card.
1. When this process has finished, safely remove the SD card and insert it into your Raspberry Pi.

## First time you power on

1. Plug in your keyboard, mouse and monitor  cables.
1. Now plug in the USB power cable to your Pi.
1. Your Raspberry Pi will boot, and a window will appear with a list of different operating systems that you can install. We recommend that you use Raspbian – tick the box next to Raspbian and click on `Install`.
1. Raspbian will then run through its installation process. *Note this can take a while.*
1. When the install process has completed, the Raspberry Pi configuration menu (`raspi-config`) will load. Here you are able to set the time and date for your region and enable a Raspberry Pi camera board, or even create users. You can exit this menu by using `Tab` on your keyboard to move to `Finish`.
