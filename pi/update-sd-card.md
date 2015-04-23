# Updating and Upgrading your SD Card

Keeping the software on your sd card up to date is often a good starting point for any project and is very simple to do. Your Raspberry Pi will need to be connected to the internet via an ethernet cable or wifi in order for these steps to work.

## Update

You will need to type a command into a terminal window or on the command line once you have logged into your Pi. 
 
1. Open a **Terminal** window by clicking on **Main Menu**, **Accessories** and **Terminal**. Alternatively you can click on the terminal icon in the taskbar.
1. Next type the following:

  ```bash
  sudo apt-get update
  ```
1. Then press **Enter** on the keyboard.

You will see...

## Upgrade

Once the update process is complete, and any information abou new versions of applications are downloaded, you will need to install the upgrades. 

1. In a terminal window or on the command line type:

  ```bash
  sudo apt-get upgrade
  ```
1. Then press **Y** or **Enter** on the keyboard when asked and your upgrades will be installed.

