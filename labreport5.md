# Lab Report 5
## Part 1 - Debugging Scenario
The scenario will be involving the ListExamples.java file from lab 7 with the second error taken out <br>
Original Post:<br>
Hi yall, I'm getting a bunch of errors when I run my tests and I don't know whats going on, can someone help?<br>
![post](/images/post.png) <br>
Below is my code and file directory: <br>
```
import java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
  }


  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      // change index1 below to index2 to fix test
      index2 += 1;
    }
    return result;
  }


}
``` <br>
![fileDirectory](/images/fileDirectory) <br>
## TA Response
Try using the java debugger to see exactly where the exceptions get thrown. To use the debugger, go to your bash script that you used to compile and run the java program. Add the -g flag after javac and replace the java command with jdb. Also replace the -cp in the java command with -classpath. Once you run the script with the updates, use ```stop at ListExamples:linenumber``` to set a breakpoint and run to run the program. Use the next command to go line by line and see where the exception gets thrown. 


