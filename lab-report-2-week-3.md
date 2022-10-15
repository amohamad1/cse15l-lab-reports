### Lab Report 2: Servers and Bugs

## Part 1:

The following is the code for the search engine:

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    
    ArrayList<String> theStrings = new ArrayList<String>();
    String s;
    

    public String handleRequest(URI url) {
        
        if (url.getPath().equals("/")) {
            return String.format("Welcome to the search engine");
        }
        else if (url.getPath().contains("/search")) {
            String[] parameters1 = url.getQuery().split("=");
            if (parameters1[0].equals("s")) {
                s = parameters1[1];
                String found = "";
                for( String aString : theStrings ){

                    if(aString.contains(s)){
                        found = found + aString+"\n";
                    }

                }
                return String.format(found);
            }
        }
         else{
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters2 = url.getQuery().split("=");
                if (parameters2[0].equals("s")) {
                    theStrings.add(parameters2[1]);
                    return String.format("Added to list!");
                }
            }
            return "404 Not Found!";
        }
        
        return "error";
    }
}

class SearchEngine {
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

Screenshots:

![Image](https://amohamad1.github.io/cse15l-lab-reports/part1/add1.png)

In the screenshot above, we add a word to our list. This calls the handleRequest(), which looks at the url for keywords. Since it finds "add" in the url, the conditional runs the code that adds the value of s in the quarey to the theStrings arraylist, which holds the words to be searched through. We continue adding more words:

![Image](https://amohamad1.github.io/cse15l-lab-reports/part1/add2.png)
![Image](https://amohamad1.github.io/cse15l-lab-reports/part1/add3.png)
![Image](https://amohamad1.github.io/cse15l-lab-reports/part1/add3.png)
![Image](https://amohamad1.github.io/cse15l-lab-reports/part1/add4.png)

The same process as add from above applies here. We then attempt to search through the arrayList of words:

![Image](https://amohamad1.github.io/cse15l-lab-reports/part1/search1.png)

In the screenshot above, we type the substring that we want to find. Notice that only strings containing that substring are found. Similar to "add", this calls the handleRequest() method. Since it finds "/search" in the url, it gets the string value of s in the quarey. It then goes through each string in theStrings arraylist and finds all elements with that substring.

## Part 2:

Bug 1: 

![Image](https://amohamad1.github.io/cse15l-lab-reports/part2/test1.png)
![Image](https://amohamad1.github.io/cse15l-lab-reports/part2/test1Output.png)
![Image](https://amohamad1.github.io/cse15l-lab-reports/part2/fixedCode1.png)

describe

Bug 2:

![Image](https://amohamad1.github.io/cse15l-lab-reports/part2/test2.png)
![Image](https://amohamad1.github.io/cse15l-lab-reports/part2/test2Output.png)
![Image](https://amohamad1.github.io/cse15l-lab-reports/part2/fixedCode2.png)

describe


