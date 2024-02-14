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

Running the JUnit tests will result in the testHandleRequest_NullURI test failing with a NullPointerException, while the testHandleRequest_ValidURI test will pass successfully.

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

### Option 2: -i (Case-insensitive search)
```
grep -i "pattern" file.txt
```
This command performs a case-insensitive search for the specified pattern in the file.txt. It ignores the case of letters, making the search more flexible.

Example 1: 

<img width="711" alt="-i caseinsensitiveex1" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/d189145e-0d38-40a4-a7b2-374a6c1a932c">

Example 2:

<img width="800" alt="Screenshot 2024-02-13 at 6 26 11 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/eae7188c-4b7b-426a-8dcd-d96358fe81ad">


### Option 3: -n (Display line numbers)
```
grep -n "pattern" file.txt
```
This command displays line numbers along with the lines containing the specified pattern in file.txt. It helps in quickly locating the occurrences of the pattern within the file.

Example 1:

<img width="714" alt="Screenshot 2024-02-13 at 6 35 32 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/d43ec25d-ff5a-4e30-9dad-032dde878439">


Example 2: 

<img width="714" alt="Screenshot 2024-02-13 at 6 36 02 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/599634b7-5c0c-49fb-a700-5e8fe9e34171">



### Option 4: -v (Invert match)
```
grep -v "pattern" file.txt
```
This command prints all lines that do not contain the specified pattern in file.txt. It's useful for filtering out unwanted lines from the output.

These options provide enhanced functionality to the grep command, allowing for more efficient and flexible text searches in files and directories.









