# Lab Report 2: Servers and SSH Keys (week 4)
---
## Part 1:

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler{
  String str = "";

  public String handleRequest(URI url){
    if (url.getPath().equals("/add-message"){
      String[] parameters = url.getQuery().split("&");

      String[] userParam = parameters[1].split("=");
      String[] messageParam = parameters[0].split("=");
      String[] user = userParam[1];
      String[] message = messageParam[1];
      str += String.format("%s: %s\n", user, message);
      return str;
    }
    return "404 Not Found!";
  }
}

class ChatServer{
  public static void main(String[] args) throws IOException{
    if(args.length == 0){
      Systerm.out.println("Missing port number! Try any number between 1024 to 49151");
      return;
    }
    int port = Interger.parseInt(args[0]);
    Server.start(port, new Handler());
  }
}
```
---
## Part 2:
1)!['ls' through SSH(my machine)](http://github.com/Domenicj1/cse15l-lab-reports/assets/146692334/c5d6079a-eef9-4df0-bb54-e9e272375109)
2)!['ls' through SSH(ieng6 machine](https://github.com/Domenicj1/cse15l-lab-reports/assets/146692334/1e1ab46a-0a32-4305-a4df-306f1b2d0f44)
3)!['ssh' without password](https://github.com/Domenicj1/cse15l-lab-reports/assets/146692334/3fbd2bc4-1e4d-44b3-b738-7881e8b21876)
---
## Part 3:
I learned that files and data can be shared and or transfered from one machine to another. Through the usage of the 'ssh' commands in a terminal I was able to manipulate the filesystem of a remote server and transfer files.
