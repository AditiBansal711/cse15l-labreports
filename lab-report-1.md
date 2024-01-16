# **Lab Report - 1**

Testing cd, ls and  cat commands.


# cd
cd - 'change directory'
 
### 1. Using 'cd' with a folder as an argument
    

Working directory: /home/lecture1

Directory After Command Execution: /home/lecture1/messages/
```
[user@sahara ~/lecture1]$ cd messages
[user@sahara ~/lecture1/messages]$ pwd
/home/lecture1/messages
```
When cd is used with a folder as an argument, the working directory is 
changed to the specified folder.

### 2. Using cd with a file as an argument

Working directory is /home/lecture1/messages/
```
[user@sahara ~/lecture1/messages]$ cd en-us.txt 
bash: cd: en-us.txt: Not a directory
```
When 'cd' is used with a file as an argument results in an error as
'cd' is designed to change directories,

and specifying a file as an argument is not valid.

### 3. Using 'cd' without an arguement

Working directory: /home/lecture1/messages/

Directory After Command Execution: /home/
```
[user@sahara ~/lecture1/messages]$ cd
[user@sahara ~]$ pwd
/home
  ```
When cd is used without any arguments, the working directory is changed to /home.


# ls

ls- 'list'

### 1. Using 'ls' with a folder as an argument

Working directory: /home/
```
[user@sahara ~]$ ls lecture1
  Hello.class  Hello.java  messages  README
```

When ls is used with a folder as an argument, the contents of the specified 
folder are displayed.


### 2. Using 'ls' with a file as an arguement

Working directory: /home/
```
[user@sahara ~]$ ls lecture1/Hello.java
lecture1/Hello.java
[user@sahara ~]$ ls ./lecture1/Hello.java
./lecture1/Hello.java
```

When ls is used with a file as an argument, the path of the file is displayed,
as input in the argument(i.e. path is not resolved).

This behavior is exhibited as ls cannot “list” the contents of a file. 
Since the file contains no files within itself, the file path, as given in the argument is displayed.

### 3. Using 'ls' without an arguement

When ls is used without any arguments, the contents of the working directory are displayed.

Working directory: /home/lecture1/
```
[user@sahara ~/lecture1]$ ls
  Hello.class  Hello.java  messages  README
```
The default argument that ls takes when no other argument is explicitly specified is ./ or the present directory.

# cat
cat - 'concatenate'

### 1. Using 'cat' with a folder as an argument

Working directory: /home/lecture1/

```
  [user@sahara ~/lecture1]$ cat messages/
  cat: messages/: Is a directory
```
When cat is used with a folder as an argument, an error is displayed as follows. 
Error occurs as 'cat' expects a file as an arguement, it cannot handle directories.


### 2. Using 'cat' with a file as an arguement

Working directory: /home/lecture1/

```
  [user@sahara ~/lecture1]$ cat Hello.java
  import java.io.IOException;
  import java.nio.charset.StandardCharsets;
  import java.nio.file.Files;
  import java.nio.file.Path;
  
  public class Hello {
    public static void main(String[] args) throws IOException {
      String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
      System.out.println(content);
    }
  }
```

 When 'cat' is used, it displays the content of the specified file, it is useful to view the contents of a file without opening it.
 
The command cat takes one or more file-paths as arguments, which are all concatenated, or joined end to end and displayed in the order they were specified.
example:

Working directory: /home/lecture1
```
[user@sahara ~/lecture1]$ cat ./messages/en-us.txt ./messages/es-mx.txt ./messages/zh-cn.txt 
Hello World!
¡Hola Mundo!
你好世界
```



### 3. Using 'cat' with no arguments

Working directory is /home/lecture1/
```
  [user@sahara ~/lecture1]$ cat
  Input
  Input
  ^C
  ```

When cat is used with no arguments,it is not valid or seems to do nothing.

The key combination Ctrl+C acts as an interrupt and breaks out of this loop.




