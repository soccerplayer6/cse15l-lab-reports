# Lab Report 3
## Part 1 - Bugs
The bug I will be choosing for week 4's lab is the bug in the averageWithoutLowest function in the week 4 lab. The objective of the function was to return the average the array that was passed in, leaving out the lowest number when calculating the average <br>
The original code for the function is below <br>
```
static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
```
## Failure Inducing Input
Some failure inducing input for this function is below: <br>
```
  @Test
  public void testAv2()
  {
    double[] arr = {2.0,2.0,2.0};
    assertEquals(2.0,ArrayExamples.averageWithoutLowest(arr),0.00001);
  }
```
![testfailed](/images/testfailed.png) <br>
In this case, the average of the function is returned as 0 even though it should be 2. The function incorrectly removes every instance of the lowest number instead of just one instance. <br>
## Input that doesnt induce a failure
A test for input that doesn't induce a failure is below: <br>
```
  @Test
  public void testAv1()
  {
    double [] arr1 = {1.0,2.0,3.0};
    assertEquals(2.5,ArrayExamples.averageWithoutLowest(arr1),0.00001);
  }
```
![testpassed](/images/testpassed.png) <br>
The only test case that failed is the testAv2 test function which was from above. The test function testAv1 didn't fail <br>
## Code before fixing the bug
```
static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
```
## Code After fixing the bug
```
static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    boolean lowestFlag = false;
    for(double num: arr) {
      if (lowestFlag == false)
      {
        if (num == lowest)
        {
          lowestFlag = true;
        }
      }
      else { sum += num; }
    }
    return sum / (arr.length - 1);
  }
```
![fixed](/images/fixed.png) <br>
The fix addresses the issue by creating a boolean variable called lowestFlag that is false by default and set to true when the lowest number is first found in the array. When the lowest number is first found in the array, the variable is set to true and the lowest number is correctly not added to the sum. Since lowestFlag is now true, every other element of the array will now be added to the list, even if it is another instance of the lowest number. This way if the test array is {2.0,2.0,2.0}, 2.0 is returned, not 0.0. <br>
## Part 2 - Researching Commands
The command I will be researching on is the less command. This command is interesting because when you run it to view a file it puts you into its own interactive terminal where there are other commands you can run to do things inside the file <br>
The syntax for using the command is: <br>
``` less [options] filename ```
## / command
When using the less commands with no options, it opens up the file and takes over your terminal so you can type additional commands. If you type ```/[string]```, it will search forward in the file for the string you have specified. An example is below: <br>
![searchcommand](/images/searchcommand.png) <br>
![search](/images/search.png) <br>
![search1](/images/search1.png) <br>
In this case I used it to find the word "at" in the chapter-1.txt file in the ```technical/911report``` directory <br>
![search5](/images/search5.png) <br>
![search3](/images/search3.png) <br>
![search4](/images/search4.png) <br>
In this case it was used to find the word "in" in the chapter-2.txt file in the  ```technical/911report``` directory <br>
This command is useful because searching for words in files and seeing where they are used is a commonly needed thing when searching through files <br>
[Source](https://phoenixnap.com/kb/less-command-in-linux) <br>
## Option -J
When used with the less command, the -J option adds a column on the left of the screen that shows which lines have the words that you searched for using the ```/``` command. <br>
The command is used as follows: ```less -J filename``` <br>
![-Jcommand](/images/-Jcommand.png) <br>
![J1](/images/J1.png) <br>
In this case the ```/at``` command was used to find words in the file with "at" in them and the -J command added a column on the left where it shows which lines have occurrences of "at". Below is another example with a different file <br>
![J2](/images/J2.png) <br>
![J3](/images/J3.png) <br>
In this case, the ```/in``` command was used to search for words with "in" in them. The -J option displayed the column on the left that shows which lines have occurences of "in". This feature is useful because if there is a big file and there aren't many occurences of the word it can make it easy to find the lines that have the word in them. <br>
[Source](https://phoenixnap.com/kb/less-command-in-linux) <br>
## Option -N
When used with the less command, the -N option will display line numbers along with the contents of the file. The command is used as follows: <br>
```less -N filename``` <br>
![J4](/images/J4.png) <br>
![J5](/images/J5.png) <br>
Above is an example of the command being used with the chapter-1.txt file. 
![J6](/images/J6.png) <br>
![J7](/images/J7.png) <br>
Above is an example of the command being used with the chapter-2.txt file. This command is useful because having line numbers can be useful when trying to find your place in a file. Referring to a line by its line number is standard <br>
[Source](https://phoenixnap.com/kb/less-command-in-linux) <br>
## Option -p
When used with the less command, the -p command can be used to open a file at the first occurrence of the word that you specify. The command is used like this: <br>
```less -p[word] filename``` <br>
![p](/images/p.png)<br>
![p1](/images/p1.png) <br>
In the above case, the file was opened, and the string "Logan" was search for and the line containing the first occurrence of "Logan" was displayed as the first line. Another example is below: <br>
![p2](/images/p2.png) <br>
![p3](/images/p3.png) <br>
In the above example the -p option was used with a different file and the word "transliteration" was searched for. This command is useful if you were looking for a specific word and wanted to open the file exactly where the first occurence of that word was.  <br>
[Source](https://phoenixnap.com/kb/less-command-in-linux) <br>
