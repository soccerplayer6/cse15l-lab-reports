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
## Option -g
When used with the less command, the -g option highlights the string that was last found when using the ```/``` command <br>
