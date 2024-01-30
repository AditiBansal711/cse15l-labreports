# LAB REPORT 2
## TASK 1: Building a ChatServer

Q1)What methods in your code are called?
My code uses 3 methods:
```handleRequest```:This method is in the Handler class and is called when the server receives a request to the /add-message path.
```ChatHistory```:This method is in the Handler class and is called within handleRequest to construct and return the full chat history after a new message is added.
```main```:This method is in the ChatServer class andis the entry point of the ChatServer program. It is called when the server application is started.


Q2)What are the relevant arguments to those methods, and the values of any relevant fields of the class?
For handleRequest(URI url):The URI url part takes in a URL as the argument. The URL in this case would be https://0-0-0-0-4001-ptlc58ci4hbh3djvp2vh064cj4.us.edusercontent.com/add-message?s=Hello&user=jpolitz.
For ChatHistory(): There are no arguments for this method. It iterates over the arr ArrayList filed to build the chat history.
For main(String [] args): This method takes in the arguments from the command-line where args[0] is expected to be the port number on which the Server should listen.


Q3)How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
In the Handler class, the arr ArrayList field is initially empty but upon receving the request, the handleRequest method parses the query and constructs the message "jpolitz: Hello" and adds it to the ArrayList arr. When it comes to local variables, the following variables get updated:

query:This variable will hold the full query string s=Hello&user=jpolitz extracted from the url.
param:This array will be populated with the split results of the query string ["s=Hello", "user=jpolitz"].
messageParam:This variable will hold the message part of the query, s=Hello.
userParam: This variable will hold the user part of the query, user=jpolitz.
message:After extracting the substring from messageParam, this will hold Hello.
user:After extracting the substring from userParam, this will hold jpolitz.
allMessages: This variable is in the ChatHistory method and is a string that starts as an empty string and accumulates all chat messages from the ArrayList arr. After the request, it will hold jpolitz: Hello\n. In the ChatServer class, the main method accepts the port number as args[0].