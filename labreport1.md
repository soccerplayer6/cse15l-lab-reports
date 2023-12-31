# Basic Filesystem Commands <br>
## File system used for the examples below: <br>
![Image](filesystem.png) <br>
In the screenshots below, the pwd command will be used to print the current working directory before and after each command has been run <br>
## cd command <br>
- With no arguments <br>
![Image](cd no path.png) <br>
The cd command with no path specified as an argument changed the working directory from lecture1 to the home directory, as seen above. The working directory before the command was /home/lecture1 and the working directory after was the home directory. The cd command itself changes the working directory to the home directory. This is the expected result and isn't an error <br>
- With a path to a directory as an argument <br>
![Image](cd with path.png) <br>
The cd command with a path specified switches the working directory to the directory of that path. The working directory before the command was the home directory and the working directory after the command was the directory of the path that was specified. This is not an error and is the intended result <br>
- With a path to a file as an argument <br>
![Image](cd path to file.png) <br>
The working directory before the command was /home and the working directory after the command was /home, so it didn't change. The command returned an error because the cd command is used to switch directories, and a file is not a directory <br>
## ls command
- With no arguments <br>
![Image](ls no path.png) <br>
As seen above, typing the ls command with no argument lists the folders/files of the current directory you are in. In this case, the home directory contains the lecture1 folder. The working directory before and after the command did not change. This isn't an error and is meant to happen. <br>
- With a path to a directory as an argument <br>
![Image](ls with path.png) <br>
As seen above, typing the ls command with a path as an argument lists the folders/files of the directory specified in the argument. In this case, it lists the files/folders of lecture1. The working directory stayed the same before and after the command was run, and the output was not an error. <br>
- With a path to a file as an argument <br>
![Image](ls path to file.png) <br>
As seen above, typing the ls command with a path to a file as an argument simply outputs the file path specified in the argument. This is not an error, as the ls command is supposed to list all the files in the directory and a path to a file is used as an argument. Again, the working directory didn't change from before the command was run. <br>
## cat command
- With no arguments <br>
![Image](cat no path.png) <br>
Typing the cat command by itself with no arguments puts the terminal into an interactive mode where anything the user types is echoed back. In the above screenshot the user typed hello and echo, which were both echoed back. The mode was exited when the user used ctrl+C. The working directory was not changed during this process, and the process was not an error. <br>
- With a path to a directory as an argument <br>
![Image](cat with path.png) <br>
Typing the cat command with a path to a directory as an argument simply outputs that the path is a directory. The working directory is not changed during this process. The output in this case is an error because the cat command is used to print out the contents of a file, and not to print out the contents of a directory<br>
- With a path to a file as an argument <br>
![Image](cat path to file.png) <br>
Typing the cat command with a path to a file as the argument outputs the content of the file as shown above. The contents of the en-us.txt file were "Hello World!" which is what was outputted. The working directory did not change. This is not an error and works exactly as intended. 


