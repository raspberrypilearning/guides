## Schedule taking pictures with bash script

Now you have a Bash script which takes pictures and timestamps them, you can schedule the script to be run at an interval, say every minute.

To do this we'll use `cron`. First open the cron table for editing:

```bash
sudo crontab -e
```

If you've not run `crontab` before you'll be prompted to select an editor - if you don't know the difference, choose `nano` by hitting `Enter`.

Now you'll see the `cron` file, scroll to the bottom where you'll see a line with the following column headers:

```bash
# m h  dom mon dow   command
```

The layout for a cron entry is made up of six components:

Minute, Hour, Day of Month, Month of Year, Day of Week and the command to be executed.

```
# * * * * *  command to execute
# ┬ ┬ ┬ ┬ ┬
# │ │ │ │ │
# │ │ │ │ │
# │ │ │ │ └───── day of week (0 - 7) (0 to 6 are Sunday to Saturday, or use names; 7 is Sunday, the same as 0)
# │ │ │ └────────── month (1 - 12)
# │ │ └─────────────── day of month (1 - 31)
# │ └──────────────────── hour (0 - 23)
# └───────────────────────── min (0 - 59)
```

To schedule for the `camera.sh` script to be executed every minute, add the following line:

```bash
* * * * * /home/pi/camera.sh 2>&1
```

Now save and exit. If you're using `nano` as your editor, that's `Ctrl + O` to save and `Ctrl + X` to exit.

You should see the following message:

```bash
crontab: installing new crontab
```

Now return to the camera directory to see the photos start to appear:

```bash
cd ~/camera/
```

and use `ls` to see the contents of the folder. Enter `date` to see how close you are to the minute (`00` seconds) as a new picture should be captured at this precise time.

Use `watch ls` to see changes to the contents of the folder. `watch` runs the command runs every 2 seconds (by default).
