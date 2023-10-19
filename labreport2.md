# Lab Report Week 3

## Part 1
## Code for StringServer
![servercode](/images/servercode.png) <br>
![servercode1](/images/servercode1.png) <br>
## Using add-message
![addmessage](/images/addmessage.png) <br>
In this screenshot, first the main function is called where the port number is passed in as input. The main function instantiates an instance of the Handler class where the handleRequest function is called, passing in the path as a URI object. Since the path after the URL contains /add-message, the text after the query is split using the by an = sign using the .getQuery() and .split() methods. If the part after the ? mark and before the = sign is equal to "s",then the string is concatenated with the string after the = sign, and the counter variable is incremented and concatenated to the string. <br>
![addmessage1](/images/addmessage1.png) <br>
In this screenshot, the handleRequest function is again called, with /add-message again being part of the path. The text after the query is again split using an = sign with the .getQuery() method getting the text after the ? sign and the .split() method getting the text before and after the = sign. The counter variable is then incremented and concatenated to the string. <br>
