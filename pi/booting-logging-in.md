# Booting and Logging into your Raspberry Pi 

The Raspberry Pi does not have an on or off switch. To power on your Pi:

1. Make sure that you have plugged in all the cables and accessories you require, and have loaded software onto an SD card and inserted it.
1. Then plug in the power cable and you will see the lights on the Raspberry Pi appear. You should then see text appear on your display.

  *Note that if you do not see any text on your screen, it may be because you did not turn it on before powering up your Raspberry Pi.*

1. Once your Raspberry Pi has completed the boot process, it will usually log you in to the graphical user interface (desktop) for user `pi`.

1. On old versions of Raspbian, or if you changed what happens on start-up in the Raspberry Pi Configuration tool, you may need to do the following steps. 

  1. A login prompt may appear. 
  
    The default login for Raspbian is username `pi` with the password `raspberry`. 
    *Note you will not see any writing appear when you type the password. This is a security feature in Linux.*
  
  1. After you have successfully logged in, you may see the command line prompt 
  
    ```bash
    pi@raspberrypi~$
    ```
    This lets you know that you are logged into your Pi. From here you can interact with your computer using only text commands. See [The Command Line](command-line-guide.md) guide to learn more.
  
  1. To load the graphical user interface, type `startx` and press `Enter` on your keyboard.
