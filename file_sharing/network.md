# Sharing files over a Windows network

If you have access to a Windows network and a file server, you can share files by placing them into a shared folder on the network.

1. You'll need some software from the Raspbian repositories to begin with. Open up LXTerminal and type the following:

		```bash
		sudo apt-get smbclient smbfs
		```

2. Now you need to create a directory where you can mount the shared folder.

		```bash
		sudo mkdir /media/share
		```

3. To mount the shared folder you can type the following command, but you'll need to know the name of the file server you are using.

		```bash
		mount –t cifs –o username=Your_Username,password=Your_Password //Name_File_Server/Path/To/Folder /media/share
		```

4. Now you can copy the files you want to share into the mounted folder, and they'll be available to everyone on the Windows network.

		```bash
		cp name_of_file /media/share/.
		```
