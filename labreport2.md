# LAB REPORT 2
## TASK 1: Building a ChatServer
### CODE:
```import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
class Handler implements URLHandler{
    
    ArrayList<String> arr=new ArrayList<>();

    public String handleRequest(URI url){

        if(url.getPath().equals("/add-message")){
            String query=url.getQuery();
            String [] param=query.split("&");
            String messageParam=param[0];
            String userParam=param[1];

        if(messageParam.startsWith("s=") && userParam.startsWith("user=")){
        
                String message=messageParam.substring(2);
                String user=userParam.substring(5);
                arr.add(user+": "+message);
                return ChatHistory();
               
            }
        }
        return "404 Not Found!";
        
    }
    public String ChatHistory(){
        String allMessages="";
        for(String s:arr){
            allMessages+=s+"\n";
        }
        return allMessages;
    }
    

}

class ChatServer{
        public static void main(String[] args) throws IOException {
            if(args.length == 0){
                System.out.println("Missing port number! Try any number between 1024 to 49151");
                return;
            }
    
            int port = Integer.parseInt(args[0]);
    
            Server.start(port, new Handler());
        }
    }
```
### FIRST OUTPUT:

<img width="1512" alt="Screenshot 2024-01-30 at 3 11 14 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/fc0093e9-b6cd-4f38-8022-47b3a43c2d1c">

## What methods in your code are called?

```handleRequest```:This method is in the Handler class and is called when the server receives a request to the /add-message path.
```ChatHistory```:This method is in the Handler class and is called within handleRequest to construct and return the full chat history after a new message is added.
```main```:This method is in the ChatServer class andis the entry point of the ChatServer program. It is called when the server application is started.


## Q2)What are the relevant arguments to those methods, and the values of any relevant fields of the class?
For handleRequest(URI url):The URI url part takes in a URL as the argument. The URL in this case would be https://0-0-0-0-4001-ptlc58ci4hbh3djvp2vh064cj4.us.edusercontent.com/add-message?s=Hello&user=jpolitz.
For ChatHistory(): There are no arguments for this method. It iterates over the arr ArrayList filed to build the chat history.
For main(String [] args): This method takes in the arguments from the command-line where args[0] is expected to be the port number on which the Server should listen.


## Q3)How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
In the Handler class, the arr ArrayList field is initially empty but upon receving the request, the handleRequest method parses the query and constructs the message "jpolitz: Hello" and adds it to the ArrayList arr. When it comes to local variables, the following variables get updated:

query:This variable will hold the full query string s=Hello&user=jpolitz extracted from the url.
param:This array will be populated with the split results of the query string ["s=Hello", "user=jpolitz"].
messageParam:This variable will hold the message part of the query, s=Hello.
userParam: This variable will hold the user part of the query, user=jpolitz.
message:After extracting the substring from messageParam, this will hold Hello.
user:After extracting the substring from userParam, this will hold jpolitz.
allMessages: This variable is in the ChatHistory method and is a string that starts as an empty string and accumulates all chat messages from the ArrayList arr. After the request, it will hold jpolitz: Hello\n. In the ChatServer class, the main method accepts the port number as args[0].
### SECOND OUTPUT 
<img width="1512" alt="Screenshot 2024-01-30 at 3 11 43 PM" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/fb4ff9d9-fb24-4ca1-922e-528aea14fc98">

# SSH KEYS
## Private key with ls
<img width="254" alt="image" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/6bbc0f1a-573c-47b7-9bd8-d66b7d268b0c">



## Public key with ls 
<img width="645" alt="image" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/7ad7ccd8-c026-4820-8147-e2127c8d591d">



## ieng6 without using password
<img width="692" alt="image" src="https://github.com/AditiBansal711/cse15l-labreports/assets/156236164/f2df6fac-4080-42ed-9e2f-58c9d8437d00">


# What I learned This week

During Week 2, I learnt about the URLHandler interface and about the different parts of a URL. I also learnt about what a port is and what ports people usually use to build websites(80 or 443). Addtionally, I learnt how to build my own Server using simple Java Code. I also learnt a few more commands such as curl and how I could access URL’s using the curl command. Building the Search Engine was really interesting!  
During Week 3, I learnt about using SSH keys for easy access into my course-specific account. I also learnt 2 new comments-scp to securely copy and mkdir to make a directory.

