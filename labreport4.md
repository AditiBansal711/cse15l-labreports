# Lab Report 4 - Vim 

## Step 4: Log into ieng6

I log into my ieng account, I don't need a password as I have already generated a private key and stored it.

<img width="1032" alt="Screenshot 2024-02-27 at 5 41 16 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/315d8cf0-4ea1-4bd5-8956-d73ca4e84884">


## Step 5: Clone your fork of the repository from your Github account (using the SSH URL)

I need to git clone lab7 with ssh . After typing ```git clone git@github.com:AditiBansal711/lab7.git```, press ```<enter>```.

<img width="1032" alt="Screenshot 2024-02-27 at 5 55 48 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/c45fc432-74a7-4a0d-b3bb-7243c9ffe32e">

## Step 6: Run the tests, demonstrating that they fail

Before compiling, we ```cd lab7``` and press ```<enter>``` to run the java programs in that directory.

<img width="1032" alt="Screenshot 2024-02-27 at 12 49 51 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/6b41e058-0339-43b3-86dd-80c0228b45cc">

## Step 7: Edit the code file to fix the failing test

To edit the file I type in ```vim ListExamples.java``` in the terminal and then press ```<enter>```, which opens the buggy code in vim tutor. 
After which using ```<j>``` key to move down to line 44, I use the command multiple(43) times, on reaching the bug, I use ```<shift + A >``` to go into editing mode, this command helps us to edit the line on which it was called. Then I use ```<l>``` key to go left and change the code as intended, ie. ```index1 += 1``` is changed to ```index2 += 1```. To get out of the editing mode, I press ```<esc>``` key. This complets the edit after which I use```:wq``` command in normal mode to save the changes and exit vim.

<img width="761" alt="Screenshot 2024-02-27 at 6 02 17 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/4a785999-5fb7-4d84-9fe9-d822d110320b">


## Step 8: Run the tests, demonstrating that they now succeed

I use the following commands ```javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java``` , ```<enter>```,then ```java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests``` and ```<enter>```to compile and run the tests. After the bug fix, both the tests pass.

<img width="1032" alt="Screenshot 2024-02-27 at 12 55 03 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/33e6bb03-9b57-4f06-89c9-5955fa529508">

## Step 9: Commit and push the resulting change to your Github account (you can pick any commit message!)

After the tests sucessfuly pass, we need to commit these changes into the main branch of our repository, for which we use ```<git commit -a -m "Edited file">``` and then press ```<enter>```. It gives us the following message.

<img width="614" alt="Screenshot 2024-02-27 at 6 58 37 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/f0109c86-7ca5-4c8a-a946-dd9a0d90e8d3">

After running this command, Git will commit all changes to tracked files, and the commit message provided will be associated with the commit.








