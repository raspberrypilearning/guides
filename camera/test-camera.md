## Test the camera

With the camera module connected and enabled, enter the following command in the Terminal to take a picture:

```bash
raspistill -o cam.jpg
```

You should see a preview on screen as the picture is taken.

Now type `ls` and you should see a file called `cam.jpg`. Open your home folder in the file browser and view the image (right click and select `Open with image preview`). If there's a picture of what your camera was pointed at - then your camera works!

If your picture was upside-down this is because your camera is pointed upside-down - that's ok - sometimes it's easier to have it that way up, and you can flip the image over.

If you intend to have your camera positioned upside-down, pass in the `-hf` and `-vf` flags to horizontally and vertically flip the image (otherwise skip to Step 2):

```bash
raspistill -hf -vf -o cam2.jpg
```

Now check again, there should now be a `cam2.jpg` file. Open the image and check it's the right way up.
