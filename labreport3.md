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

