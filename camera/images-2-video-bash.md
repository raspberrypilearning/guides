# Turn still images in to a video

You can do this on the Pi using `mencoder` but the processing will be slow. You may prefer to transfer the image files to your desktop computer or laptop and processing the video there.

Navigate to the folder containing all your images and list the file names in to a text file. For example:

```bash
ls *.jpg > stills.txt
```

### On Raspberry Pi or other Linux computer

Install the package mencoder:

```bash
sudo apt-get install mencoder
```

Now run the following command:

```bash
mencoder -nosound -ovc lavc -lavcopts vcodec=mpeg4:aspect=16/9:vbitrate=8000000 -vf scale=1920:1080 -o timelapse.avi -mf type=jpeg:fps=24 mf://@stills.txt
```

This will save a video called `timelapse.avi`
