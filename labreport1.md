# Basic Filesystem Commands <br>
## File system used for the examples below: <br>
![Image](filesystem.png) <br>
In the screenshots below, the pwd command will be used to print the current working directory before and after each command has been run <br>
## cd command <br>
- With no arguments <br>
![Image](cd no path.png) <br>
The cd command with no path specified as an argument changed the working directory from lecture1 to the home directory as seen above <br>
- With a path to a directory as an argument <br>
![Image](cd with path.png) <br>
The cd command with a path specified switches the working directory to the directory of that path <br>
- With a path to a file as an argument <br>
![Image](cd path to file.png) <br>
The command returned an error because the cd command is used to switch directories, and a file is not a directory <br>
## ls command
- With no arguments <br>
![Image](ls no path.png) <br>
As seen above, typing the ls command with no argument lists the folders/files of the current directory you are in. In this case, the home directory contains the lecture1 folder <br>
- With a path to a directory as an argument <br>
![Image](ls with path.png) <br>
As seen above, typing the ls command with a path as an argument lists the folders/files of the directory specified in the argument. In this case, it lists the files/folders of lecture1. <cd>
- With a path to a file as an argument <br>
![Image](ls path to file.png) <br>
As seen above, typing the ls command with a path to a file as an argument simply outputs the file path specified in the argument.
## cat command
- With no arguments <br>
![Image](cat no path.png) <br>
Typing the cat command by itself with no arguments puts the terminal into an interactive mode where anything the user types is echoed back. In the above screenshot the user typed hello and echo, which were both echoed back. The mode was exited when the user used ctrl+C <br>
- With a path to a directory as an argument <br>
![Image](cat with path.png) <br>
Typing the cat command with a path to a directory as an argument simply outputs that the path is a directory <br>
- With a path to a file as an argument <br>
![Image](cat path to file.png) <br>
Typing the cat command with a path to a file as the argument out puts the content of the file as shown above. The contents of the en-us.txt file were "Hello World!" which is what was outputted. The working directory did not change. 


