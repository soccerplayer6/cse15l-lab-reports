# Lab Report 3
## Part 1 - Bugs
``` 
static void reverseInPlace(int[] arr) { 
    int [] temp = new int[arr.length]; 
    for (int i=0;i < arr.length;i++)  
    { 
      temp[i] = arr[i]; 
    } 
    for(int i = 0; i < arr.length; i += 1) { 
      arr[i] = temp[arr.length - i - 1]; 
    } 
  } 
  ```
  
