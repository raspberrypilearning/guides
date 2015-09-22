# Sharing files via a Python server

Python provides an easy method of setting up a simple http server, allowing you to share files with others, accessible via a web browser or wget.

1. The first thing you'll need is the IP address of you Raspberry Pi. Open up LXTerminal and type:

		```bash
		hostname -I
		```

2. The IP address needs to be shared with those that need access to the files.

3. Next you need to make sure you are in the directory containing the file or files to be shared.

		```bash
		cd name/of/directory
		```

4. Now you need to start the Python server.

		```bash
		python3 -m http.server
		```

5. All the files in your current directory are now available to anyone on your network. To access the files they can open up a webbrowser and type your Pi's IP address along with `:8000/name_of_file`. For instance:

		```
		192.168.1.123:8000/name_of_file
		```
6. The webbrowser will either display the file (if html or txt) or download the file.

8. Alternatively the file can be collected using wget, if the people you are sharing with are using a Unix based system or Putty.

		```bash
		wget 192.168.1.123:8000/name_of_file
		```
