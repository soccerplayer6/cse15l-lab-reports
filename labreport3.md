# Lab Report 3
## Part 1 - Bugs
`` 
static void reverseInPlace(int[] arr) { <br>
    int [] temp = new int[arr.length]; <br>
    for (int i=0;i < arr.length;i++)  <br>
    { <br>
      temp[i] = arr[i]; <br>
    } <br>
    for(int i = 0; i < arr.length; i += 1) { <br>
      arr[i] = temp[arr.length - i - 1]; <br>
    } <br>
  } <br>
  ``
  
