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









