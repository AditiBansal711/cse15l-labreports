# Lab Report 3 - Bugs and Commands 

## PART1 - Bugs

### 1. Failure inducing program
```
import org.junit.Test;
import static org.junit.Assert.assertEquals;

public class ChatHandlerTest {

    @Test(expected = NullPointerException.class)
    public void testHandleRequest_NullURI() {
        ChatHandler handler = new ChatHandler();
        handler.handleRequest(null);
    }
}
```
This test checks if the handleRequest() method of ChatHandler throws a NullPointerException when passed a null URI.

### 2. Input that doesn't induce a failure
```
import org.junit.Test;
import java.net.URI;
import static org.junit.Assert.assertEquals;

public class ChatHandlerTest {

    @Test
    public void testHandleRequest_ValidURI() {
        ChatHandler handler = new ChatHandler();
        String response = handler.handleRequest(URI.create("http://localhost:4000/chat?username=user&message=hello"));
        assertEquals("", response); // Assuming the initial chat history is empty
    }
}
```
This test checks if the handleRequest() method of ChatHandler returns an empty string when passed a valid URI.

   
### 3.Symptom

Running the JUnit tests will result in the testHandleRequest_NullURI test failing with a NullPointerException, while the testHandleRequest_ValidURI test will pass successfully.

### 4.Bug Fix 
```
public String handleRequest(URI url) {
    if (url == null) {
        throw new IllegalArgumentException("URI cannot be null");
    }
    // Existing code remains unchanged
}
```
### 5.Description
The bug occurs because the handleRequest() method doesn't handle null URIs properly, leading to a NullPointerException when trying to access properties of the URI object. By adding a null check for the URI parameter, we ensure that the method fails fast and provides a more meaningful error message instead of throwing a NullPointerException.

# Part 2 - Researching Commands

## Command: grep

### Option: -i (ignore case)

Source: Linux grep Command Usage with Examples

### 1.Example on files:
```
grep -i "hello" file.txt
```
This command searches for the string "hello" in the file.txt file, ignoring case sensitivity.

### Output:
```
Hello world
hello there
```
Explanation: The -i option ensures that the search is case-insensitive, so both "Hello" and "hello" are matched.

### 2.Example on directories:
```
grep -ri "error" ./directory
```
This command searches for the string "error" recursively in all files within the directory directory, ignoring case sensitivity.

### Output:
```
./directory/file1.txt: Error encountered
./directory/subdirectory/file2.txt: ERROR: Something went wrong
```
Explanation: The -r option enables recursive search, while -i makes the search case-insensitive, allowing you to find instances of "error", "Error", "ERROR", etc., in the specified directory and its subdirectories.







