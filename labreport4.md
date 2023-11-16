# Lab Report 4
## Log into ieng6
To log into ieng6, I used the ```<up>``` arrow to get the last command used in my history which was ```ssh cs15lfa23gy@ieng6.ucsd.edu```.<br>
Keys pressed: ```<up><enter>``` <br>
Below is the result after pressing the keys <br>
![login](/images/login.png) <br>
## Clone fork of the repository using SSH URL
To clone the repository, I pressed the ```<up>``` arrow to go up 7 commands in my command history to run the command ```git clone git@github.com:ucsd-cse15l-s23/lab7.git```<br>
Keys pressed: ```<up><up><up><up><up><up><up><enter>``` <br>
Below is the result after pressing the keys <br>
![clone](/images/clone.png) <br>
## Run the tests, showing that they fail
I first had to change into the lab7 directory. I did this by simply typing ```cd lab7``` <br>
To run the tests, I entered the command ```bash test.sh``` to run the bash script that runs the tests. 
Commands typed: ```<cd lab7><bash test.sh>``` <br>
Below is the result after entering the commands <br>
![run](/images/run.png) <br>
## Edit the code to fix the failing test
To do this, I opened up the file in vim. I did this by typing ```vim List``` pressing ```<tab>``` to autocomplete, and then typing ```.java``` and pressing ```<enter>```<br> 
Below is the result after pressing the keys <br>
![vim](/images/vim.png) <br>
After entering vim, I typed ```<43><enter><5l><x><i><2><esc><:wq>```<br>
The ```<43>``` and ```<enter>``` brought the cursor down to the right line and the ```<5l>``` brought it to the right character. Below is where the cursor is at this point: <br>
![char](/images/char.png) <br>
I then typed ```<x>```, ```<i>```, and ```<2>```. This deleted the character the cursor was on, put vim into insert mode, and inserted 2 in the file <br>
I then typed ```<:wq>```, which saved and exited the file. <br>
Below is a screenshot of what the terminal looks like after executing these commands: <br>
![term](/images/term.png) <br>
## Run the tests, demonstrating that they now succeed
To run the tests, I pressed ```<up><up>``` to go up 2 commands in my history to where I ran the command ```bash test.sh``` previously <br>
Below is the output showing that the tests ran successfully <br>
![success](/images/success.png) <br>
## Commit and push the following changes to your github account
