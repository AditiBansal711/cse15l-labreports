# Lab Report 3 - Bugs and Commands 

## PART1 - Bugs: reversed method not properly reversing array

### 1. Failure inducing program
```
 import static org.junit.Assert.assertArrayEquals;

import org.junit.Test;

public class ArrayExamplesTest {

    @Test
    public void testReversedFailure() {
        int[] input = {1, 2, 3, 4};
        int[] expected = {4, 3, 2, 1};
        assertArrayEquals(expected, ArrayExamples.reversed(input));
    }
}
```


### 2. Input that doesn't induce a failure
```
import static org.junit.Assert.assertArrayEquals;

import org.junit.Test;

public class ArrayExamplesTest {

    @Test
    public void testReversedSuccess() {
        int[] input = {1, 2, 3, 4};
        int[] expected = {1, 2, 3, 4}; // No reversal expected
        assertArrayEquals(expected, ArrayExamples.reversed(input));
    }
}
```

### 3.Symptom

<img width="1101" alt="Screenshot 2024-02-13 at 7 31 09 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/2a049585-eb42-4d90-b16d-5000cfca2dda">

The symptom of the bug is evident in the JUnit output where two tests (testReversedSuccess and testReversedFailure) have failed. 
Both failures are due to arrays first differing at element [0], where the expected value is different from the actual value.
The failed tests indicate that the reversed method in the ArrayExamples class is not properly reversing the input array.
In both cases, the expected first element of the reversed array is 1 and 4, respectively, but the actual first element is 0.
This suggests that the method is not correctly reversing the elements of the array, leading to incorrect output.

### 4.Bug Fix 
Code before bug fix: 
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
Code after bug fix:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1]; // Fixed: assign values to newArray instead of arr
    }
    return newArray;
}
```
### 5.Description
The bug was caused by assigning values to the input array arr instead of the newly created array newArray. This caused the method to essentially overwrite the original array with the reversed values, resulting in incorrect output. By fixing the assignment to newArray, the method now correctly returns a new array with the elements reversed.

# Part 2 - Researching Commands

## Command: grep

### Option 1: -r (Recursive search)
```
grep -r "pattern" ./technical
```
This command recursively searches for the specified pattern in all files and directories within the ./technical directory. It's useful for finding occurrences of a pattern across multiple files and directories.

Example 1:

<img width="1101" alt="Screenshot 2024-02-13 at 7 04 28 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/602a7614-98de-41de-a320-cc34c61bf3de">

Example 2: 

<img width="1101" alt="Screenshot 2024-02-13 at 7 05 00 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/7aa28eca-6379-4f63-8ea2-f1c8919dde86">




### Option 2: -i (Case-insensitive search)
```
grep -i "pattern" file.txt
```
This command performs a case-insensitive search for the specified pattern in the file.txt. It ignores the case of letters, making the search more flexible.

Example 1: 

<img width="906" alt="Screenshot 2024-02-13 at 6 56 46 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/6bf80d61-caa2-404f-9417-b6e03cb1e62e">

Example 2:

<img width="906" alt="Screenshot 2024-02-13 at 6 53 20 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/bdeb620b-cf70-4913-9c80-187f2f52052b">





### Option 3: -n (Display line numbers)
```
grep -n "pattern" file.txt
```
This command displays line numbers along with the lines containing the specified pattern in file.txt. It helps in quickly locating the occurrences of the pattern within the file.

Example 1:

<img width="1101" alt="Screenshot 2024-02-13 at 7 08 16 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/527cfb4f-2a6d-47f0-bac4-73ba2fa49265">



Example 2: 


<img width="1101" alt="Screenshot 2024-02-13 at 7 09 12 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/ea5453f6-a546-4280-bcbd-1b21550d38da">



### Option 4: -v (Invert match)
```
grep -v "pattern" file.txt
```
This command prints all lines that do not contain the specified pattern in file.txt. It's useful for filtering out unwanted lines from the output.

These options provide enhanced functionality to the grep command, allowing for more efficient and flexible text searches in files and directories.

Example 1: 

<img width="1101" alt="Screenshot 2024-02-13 at 7 14 32 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/610990fb-0ca4-4290-8e38-67affb426b05">


Example 2:

<img width="1101" alt="Screenshot 2024-02-13 at 7 13 59 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/e8a1a553-f5d0-4baf-a74f-f43138c1d56e">







