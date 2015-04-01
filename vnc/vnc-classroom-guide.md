# Remote Desktop to a Raspberry Pi from a networked computer

## Step 1: Set up and install VNC server on Raspberry Pi

Install the VNC server software on Pi and the VNC viewer software on the host computer (which will show the Pi desktop).
1. On your Raspberry Pi install the TightVNC package:

  ```
  sudo apt-get install tightvncserver
  ```
1. Next, run TightVNC Server which will prompt you to enter a password and an optional view-only password:

  ```
  tightvncserver
  ```

1. Start a VNC server from the terminal. This example starts a session on VNC display zero (```:0```) with full HD resolution:

  ```
  vncserver :0 -geometry 1024x768 -depth 24
  ```

## Step 2: Install a VNC client on a computer

1. Now, on your computer, install and run the VNC client:

  - On a Linux machine install the package `xtightvncviewer`:

    `sudo apt-get install xtightvncviewer`

  - Otherwise, TightVNC is downloadable from [tightvnc.com](http://www.tightvnc.com/download.php)



## Step 3: If necessary, configure the Pi to give out an IP address

This is the method you'll want to use if your network administrator refuses to allow a Raspberry Pi to be connected to the main school network. This way each Raspberry Pi will be directly connecting to a host computer using a single Ethernet cable, thus making a completely isolated point-to-point network between the two. 

*Note: you don't need a crossover cable for this; a standard cable will work because the Pi Ethernet port auto-switches the transmit and receive pins.*

Firstly we'll need to install some software on the Pi, so for this first part you'll need to connect it to a LAN for internet access. We’re going to make the Pi Ethernet port behave in a similar way to a home router. This means assigning a static IP address to it and installing a DHCP service (`dnsmasq`) that will respond to address requests from the host computer. 

1. From the command line or an LXTerminal window type:

  ```
  sudo apt-get update
  sudo apt-get install dnsmasq
  ```
  
1. It’s a good idea to use an IP address range that is very different to your main network, so let’s use 10.0.0.X. To configure this we must edit the network interfaces file. Enter the following command:

  ```
  sudo nano /etc/network/interfaces
  ```
1. Find the line `iface eth0 inet dhcp` and add a hash symbol at the start of the line to disable it. Then add the other four lines shown below:

  ```
  # iface eth0 inet dhcp
  auto eth0
  iface eth0 inet static
  address 10.0.0.1
  netmask 255.255.255.0
  ```
  
1. Press **Ctrl** and **X** followed by **Y** then **Enter** to save and quit out of nano. The Raspberry Pi will now have a static address of `10.0.0.1`.

## Step 4: Configure **dnsmasq** to give out IP addresses

To do this first make a backup of the default config file and then save my one in its place:

1. Type `cd /etc` on the command line to change directories then press **Enter**. 
1. Next type `sudo mv dnsmasq.conf dnsmasq.default` and press **Enter**.
1. Then type `sudo nano dnsmasq.conf` and press **Enter**. You should now be editing a blank file. Type the following into it:

  ```
  interface=eth0
  dhcp-range=10.0.0.2,10.0.0.250,255.255.255.0,12h
  dhcp-option=3,10.0.0.1
  ```
  The first line tells `dnsmasq` to listen for DHCP requests on the Ethernet port of the Pi. The second line is specifying the range of IP addresses that can be given out. The third line provides the default gateway for the host computer (which won't actually be used here).

1. Disconnect the Pi from the LAN and reboot by typing `sudo reboot`.

## Step 5: Test the connection

1. After the Pi boots back up, give it a minute or so, and you can go ahead and plug in the single Ethernet cable directly from the Pi to the host computer. The host computer should then be given an IP address which will be `10.0.0.X`, where X is a random number between 2 and 250.
1. Test that there is a working connection by opening up a command prompt on the host computer (a Terminal on OSX and Linux), and enter the following command `ping 10.0.0.1`.

  If you see `reply, reply, reply `then it's working. If you see request timed out, then something is wrong and you'll need to go back and double-check everything.

1. You can now open up your VNC viewer on the host PC and connect it to the Pi. When prompted for the remote host enter   `10.0.0.1:1` and click **connect**. It could also be `10.0.0.1:0` depending on how you set it up in step 1.

  You'll be prompted for the password that you chose during step 1; after that you'll see the Pi desktop and will be able to get going with Scratch or whatever program you need. Remember that 3D games like Minecraft are not going to work using this method, as those draw their image directly to the local screen memory and will be ignored by VNC. You'll just see an empty window.
