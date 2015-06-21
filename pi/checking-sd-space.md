# Checking space on an SD card

When running `sudo apt-get upgrade`, it will show how much data will be downloaded and how much space it will take up on the SD card. It's worth checking with `df -h` that you have enough disk space free, as unfortunately apt will not do this for you. Also be aware that downloaded package files (.deb files) are kept in `/var/cache/apt/archives`. You can remove these in order to free up space with `sudo apt-get clean`.
