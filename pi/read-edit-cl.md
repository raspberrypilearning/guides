# Commands for reading and editing files

The following commands used on the command line or in a terminal window in Raspbian will help you access more information about files and help you to edit them.

## cat

The `cat` command will list the contents of a file. 

Type `cat` followed by the name of the file and press enter on your keyboard. For example `cat first-program.py` will display the contents of `first-program.py`. The command can be used to list the contents of multiple files too. For example: `cat *.txt` will list the contents of all `.txt` files in the current directory.

## head

The `head` command displays the beginning of a file. 

Type `head` followed by the name of the file and press enter. For example: `head first-program.py`. 

The command can be used with `-n` to specify the number of lines to show (by default 10), or with `-c` to specify the number of bytes.

## tail

The `tail` command displays the end of a file. 

Type `tail` followed by the name of the file and press enter. For example: `tail first-program.py`. 

The starting point in the file can be specified either through using `-b` for 512 byte blocks, `-c` for bytes, or `-n` for number of lines.

## man

The `man` command shows the manual page for a file. To find out more, type `man man` and press enter. The manual page will give your more information for the `man` command.

## nano

`nano` is a command line text editor. You can use it to either create a new file or to edit a file. 

Type `nano` followed by a name for your new file and press enter. A text editor window will open in which you can type your text. You might use this to write or ammend code. 

To quit nano press `Ctrl` and `q` on your keyboard. Followed by `y` to confirm.