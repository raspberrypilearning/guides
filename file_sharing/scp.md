# Sharing files via scp

If you are happy to give your password to those that you want to share files with (or you haven't changed the default password for Raspbian), then the easiest way to share files is via scp.

1. Open up LXTerminal and type the following command to reveal your IP address.

		```bash
		hostname -I
		```

2. The users you want to share the files with also need to open up LXTerminal. They can then type the following command to copy the file via the ssh protocol, but the IP address and filenames obviously need to be ammended for your situation. 

		```bash
		scp pi@192.168.1.123:~/path/to/file ~/.
		```

3. They'll be prompted for your password, and then the file will be copied over.
