## Week 3 Lab Report
# Adrian Wong


**Simpliest Search Engine**

Code:  

```
import java.io.IOException;
import java.util.ArrayList;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;
    ArrayList<String> list = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return "Pass an input!";
        } else if (url.getPath().equals("/increment")) {
            num += 1;
            return String.format("Number incremented!");
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    list.add(parameters[1]);
                    return String.format("added: %s", parameters[1]);
                }
            }
            else if (url.getPath().contains("/search")){
                ArrayList<String> hasString = new ArrayList<String>();
                String[] parameters = url.getQuery().split("=");
                for (String added: list){
                    if (added.contains(parameters[1])){
                        hasString.add(added);
                    }
                }
                return "String that contains " + parameters[1] + ": " + hasString.toString();
            }
            return "404 Not Found!";
        }
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

The Handler in the simpliest search engine is the method that is constantly waiting for inputs
in the url. It listens for `/add?=` to be typed in for a String to be added into the array. When
it is in default screen, it says "Pass an input!".


![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/Screen%20Shot%202022-10-14%20at%208.50.26%20PM.png) 

In this screenshot, the handleRequest method is being called. It listens for the `/add?s=pineapple`. This
is showing that it is going into the query of the URL. The String Arraylist is added to everytime
the `/add?=s____` is ran in the URL. Since it only takes in one command at a time, the runtime is not significant.

![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/Screen%20Shot%202022-10-14%20at%208.50.45%20PM.png)  

In this screenshot, the handleRequest method is being called. It listens for the `/add?s=pen`. This
is showing that it is going into the query of the URL. The String Arraylist is added to everytime
the `/add?s=____` is ran in the URL. Since it only takes in one command at a time, the runtime is not significant.

![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/Screen%20Shot%202022-10-14%20at%209.00.54%20PM.png)  

In this screenshot, the handleRequest method is being called. It listens for the `/search?s=app`. This
prints out every String in the ArrayList that contains the key word *app*.



# Bug Induced Code

1. The first bug found in the code was the code in ArrayExamples.java. In the method
`reversed`, the code is :

```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

The test fails as the output gives out the same array as its input, when
the purpose of the method is to print the list in reverse. The code 
needs to be fixed by creating a temp array, adding each element from
the back of the list, then iterating backwards with the for-loop.
Then, return that temp arr. The code in the for-loop is simply 
iterating the array from the front, and still assigning each value
from the front. Also, it returns the original input array.

2. The second bug was found in ListExamples.java. In the method 
`filter`, the code is:  
```
static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
  }
```

When you give it an input, it constantly adds the element to the front of the list.
This creates the issue where it is an infinite loop with no end, causing the terminal
to timeout from a certain amount of time. The code was fixed by changing `result.add(0, s)`
to `result.add(s)`. This allows the elements to be added to the back of the list until
it meets a certain condition of failure. The code doesn't have something checking for a
terminating condition. A terminating condition must be added such as the length of the
string be less than 3. 








