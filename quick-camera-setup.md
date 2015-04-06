# Quick Camera Setup Guide

The Raspberry Pi camera can take full HD 1080p photo and videos. It can also be programmed using code. 

## Connecting the camera

1. Take a look at the camera module. You will notice that there is a long white cable running from fromone end of the camera. This is called a flex cable and will connect the cmaera to a Raspberry Pi.
1. Next, locate the connector on your Raspberry Pi between the Ethernet and HDMI ports, with the silver connectors facing the HDMI port. See the image below to help you.
1. The connector can be opened by pulling the tabs on the top of the connector upwards then towards the Ethernet port. 
1. Once opened, insert the flex firmly into the connector. Take care not to bend the flex at too much. 
1. Finally, the top part of the connector can then be pushed towards the HDMI connector and down, while the flex cable is held in place.

Watch the following video to see a demonstration of the camera being connected:

[![Camera connection screenshot](http://img.youtube.com/vi/GImeVqHQzsE/0.jpg)](http://www.youtube.com/watch?v=GImeVqHQzsE)

*Note: The camera may come with a small piece of translucent blue plastic film covering the lens. This is only present to protect the lens while it is being mailed to you, and needs to be removed by gently peeling it off

## Enabling the camera

Open the `raspi-config` tool from the Terminal:

```bash
sudo raspi-config
```

Select `Enable camera` and hit `Enter`, then go to `Finish` and you'll be prompted to reboot.

## Using the camera

Libraries for using the camera are available in:

- [Shell](raspicam/README.md) (Linux command line)
- [Python](python/README.md)

See detailed [technical specs](../../hardware/camera.md) of the camera hardware and software.
