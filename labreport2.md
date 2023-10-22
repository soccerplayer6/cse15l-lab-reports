# Lab Report Week 3

## Part 1
## Code for StringServer
![servercode](/images/servercode.png) <br>
![servercode1](/images/servercode1.png) <br>
## Using add-message
![addmessage](/images/addmessage.png) <br>
In this screenshot, first the main method is called where the port number is passed in as input. The main method instantiates an instance of the Handler class where the handleRequest method is called, passing in the path as a URI object. Since the path after the URL contains /add-message, the text after the query is split using the by an = sign using the .getQuery() and .split() methods. If the part after the ? mark and before the = sign is equal to "s",then the string is concatenated with the string after the = sign, and the counter variable is incremented and concatenated to the string. <br>
![addmessage1](/images/addmessage1.png) <br>
In this screenshot, the handleRequest method is again called, with /add-message again being part of the path. The text after the query is again split using an = sign with the .getQuery() method getting the text after the ? sign and the .split() method getting the text before and after the = sign. The counter variable is then incremented and concatenated to the string. <br>
## Part 2
## Path to private and public keys using ls
![privatekey](/images/privatekey.png) <br>
In the above screenshot, the path to the files is shown in the pwd command. The private key is in id_rsa and the public key is in id_rsa.pub. The path to the private key is ```/c/Users/ibrah/.ssh/id_rsa```. The path to the public key is ```/c/Users/ibrah/.ssh/id_rsa```.<br>
![nopassword](/images/nopassword.png) <br>
Example of logging into ieng6 without a password <br>
## Part 3
In week 2, all the stuff I learned about Java web servers are all completely new to me. I also didn't have Java installed for Visual Studio Code, so that was new as well.
