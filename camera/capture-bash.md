## Write a script

Now we'll write a Bash script which will take a picture and save it with the date and time. It can be as simple as this:

```bash
#!/bin/bash

DATE=$(date +"%Y-%m-%d_%H%M")

raspistill -o /home/pi/camera/$DATE.jpg
```

Remember to use the `-vf` and `-hf` flags if your camera is pointed upside-down.

Create a new file called `camera.sh` by opening with a text editor, e.g. `nano camera.sh`, paste or otherwise enter the lines from above and save the file.

Now make this file executable with the following command:

```bash
chmod +x camera.sh
```

Running this script will save a picture with the timestamp as the filename in a folder called `camera` in your home directory. First we'll create this folder:

```bash
mkdir camera
```

Make sure you're in the home directory when you do this. If you're not, or you're not sure, just type `cd` and hit `Enter` to return to your home directory.

You can use `pwd` (present working directory) to verify your location and `ls` to show the contents. After running `mkdir` you should see a new folder there.

Before continuing, test the script works as intended by running it from the command line (first return to the home directory with `cd`):

```bash
./camera.sh
```

You should see the preview again as the picture is taken. Now use `ls camera` to look inside the `camera` folder to see the picture you just captured on disk.

Open the file browser and preview the image to see the picture itself. If you're happy this worked as intended, and the date and time were given in the filename, continue to automation.
