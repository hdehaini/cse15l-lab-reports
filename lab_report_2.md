# **Lab 2 Report**
### *Hamza Dehaini*

---

## Part 1

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String list = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("List: %s", list);
        }
        System.out.println("Path: " + url.getPath());
        if (url.getPath().contains("/add")) {
            String[] parameters = url.getQuery().split("=");
            System.out.println(parameters[0]);
            System.out.println(parameters[1]);
            if (parameters[0].equals("s")) {
                list += "\n-" + parameters[1];
                return String.format("Added to list!");
            }
        }

        if (url.getPath().contains("/getlist")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("finallist")) {
                return String.format("List is now: %s", list);
            }
        }

        return "404 Not Found!";
    }
}

class SearchEngine {
    public static void main(String[] args) throws IOException {
        if (args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

```

The code above creates a web-page that stores and prints out a list when commanded.

This is the first page that opens before any queries are called in the URL:

![Image](pictures\labReport2\starttlist.JPG)

---

### These images showcase when I added items to the list.



- This screenshot uses the handle request method to find "/add" in the URL.
- I then did a query "?", then used the getQuery method that splits each element in the with "=".
- The method then looks for "s" after the query, which will be the input for the first element, telling the program to input the second element (which is indicated after a "=") in the list.
- I defined the first element to be "parameters[0]" in the code which equals to "s".
- I defined the second element to be "parameters[1]" which equals to "pineapple" in this case.
- These elements change everytime we input refresh a new page. It would check the URL to see if anything changed, and if parameters[0]" is still "s", it will input what ever is in parameters[1] into the list, if it changed.
- In this case, since the second element, or parameters[1], in the URL is "pineapple", that term is then inserted into the list.

![Image](pictures\labReport2\addeddpinaple.JPG)

- This screenshot uses the handle request method to find "/add" in the URL.
- I then did a query "?", then used the getQuery method that splits each element in the with "=".
- The method then looks for "s" after the query, which will be the input for the first element, telling the program to input the second element (which is indicated after a "=") in the list.
- I defined the first element to be "parameters[0]" in the code which equals to "s".
- I defined the second element to be "parameters[1]" which equals to "apple" in this case.
- These elements change everytime we input refresh a new page. It would check the URL to see if anything changed, and if parameters[0]" is still "s", it will input what ever is in parameters[1] into the list, if it changed.
- In this case, since the second element, or parameters[1], in the URL is "apple", that term is then inserted into the list.

![Image](pictures\labReport2\appleaddsfed.JPG)

- This screenshot uses the handle request method to find "/add" in the URL.
- I then did a query "?", then used the getQuery method that splits each element in the with "=".
- The method then looks for "s" after the query, which will be the input for the first element, telling the program to input the second element (which is indicated after a "=") in the list.
- I defined the first element to be "parameters[0]" in the code which equals to "s".
- I defined the second element to be "parameters[1]" which equals to "lemon" in this case.
- These elements change everytime we input refresh a new page. It would check the URL to see if anything changed, and if parameters[0]" is still "s", it will input what ever is in parameters[1] into the list, if it changed.
- In this case, since the second element, or parameters[1], in the URL is "lemon", that term is then inserted into the list.

![Image](pictures\labReport2\lemohjnadded.JPG)

- This screenshot uses the handle request method to find "/add" in the URL.
- I then did a query "?", then used the getQuery method that splits each element in the with "=".
- The method then looks for "s" after the query, which will be the input for the first element, telling the program to input the second element (which is indicated after a "=") in the list.
- I defined the first element to be "parameters[0]" in the code which equals to "s".
- I defined the second element to be "parameters[1]" which equals to "orange" in this case.
- These elements change everytime we input refresh a new page. It would check the URL to see if anything changed, and if parameters[0]" is still "s", it will input what ever is in parameters[1] into the list, if it changed.
- In this case, since the second element, or parameters[1], in the URL is "orange", that term is then inserted into the list.

![Image](pictures\labReport2\orangeasded.JPG)

- This screenshot uses the handle request method to find "/add" in the URL.
- I then did a query "?", then used the getQuery method that splits each element in the with "=".
- The method then looks for "s" after the query, which will be the input for the first element, telling the program to input the second element (which is indicated after a "=") in the list.
- I defined the first element to be "parameters[0]" in the code which equals to "s".
- I defined the second element to be "parameters[1]" which equals to "strawberry" in this case.
- These elements change everytime we input refresh a new page. It would check the URL to see if anything changed, and if parameters[0]" is still "s", it will input what ever is in parameters[1] into the list, if it changed.
- In this case, since the second element, or parameters[1], in the URL is "strawberry", that term is then inserted into the list.

![Image](pictures\labReport2\straawwberyueaded.JPG)

---

- Finally, I do a simple query using the same method "handleRequest" as the part of adding an item to the list to then print out the entire list so far. In this screenshot, the list consists of: pinapple, apple, lemon, orange, and strawberry.
- What the function does is it uses the getPath method and checks if "/getlist" is in the URL, and then after a query "?", it searches for the term "finallist" for parameters[0] which will then tell the program to print out the list, as showcased in the screenshot.
- In this case, the program does not look for a second element after thge query for parameters[1]

![Image](pictures\labReport2\qurerryfinallists.JPG)

## Part 2

### Array Method Debug: reversed

**Failure-inducing input:**

The failure-inducing input for this method (which is supposed to return a new array that is the reversed of in inputed array) is when the length of the array is greater than 1.

It would work fine if the array contained one element or less, but dothing more.

This is the test that I made which failed:

```
@Test
  public void hamza_testReversed() {
    int[] input1 = { 0, 1, 2, 3, 4, 5 };
    assertArrayEquals(new int[]{ 5, 4, 3, 2, 1, 0 }, ArrayExamples.reversed(input1));
  }
```


**Symptom:**

The symptom was that it was returning the original version of the inputed array, rather than the reversed version.

![Image](pictures\labReport2\reverseSymptom15l.JPG)


**Bug:**

The bug was that the original array "arr" and the new array that was supposed to be outputed "newArray" were switched in the code. To fix the bug, I just changed switched them to return the new reversed array.

```
// Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```

**Connection:**

The reason that an array with 1 or 0 elements doesn't show any bad symptoms is because what we defined as the correct output is for the original array to be reversed in the new array. That being said, the reverse of an array with 1 element or 0 is itself. Even if we return the original array, we wouldn't see any bad symptoms. However, once we start adding more elements where the correct output isn't itself, returning the original array will cause problems.

---

### List Method Debug: filter

**Failure-inducing input:**

The failure-inducing input is whenever there is an input with more than one element

```
@Test
    public void testFilter() {
        List<String> input1 = new ArrayList<String>();
        input1.add("test1");
        input1.add("test22");
        input1.add("test333");
        input1.add("test4444");
        input1.add("test55555");
        input1.add("test666666");
        input1.add("test7777777");
        StringChecker sc = new StringChecker(){
            public boolean checkString(String s){
                return s.length() >= 8;
            }
        };
        input1 = ListExamples.filter(input1, sc);
        List<String> answer = new ArrayList<String>();
        answer.add("test4444");
        answer.add("test55555");
        answer.add("test666666");
        answer.add("test7777777");
       
        assertEquals(answer, input1);
    }
```

**Symptom:**

The symptom is that the method does filter through the correct elements, yet it returns them in a reverse order.

![Image](pictures\labReport2\filterSymptom15l.JPG)


**Bug:**

The bug was that the code originally inserted the filtered elements in the beginning of the list. So I took that part out to make the program add the filtered elements at the end of the list by default	

```
// Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(s);
      }
    }
    return result;
  }
```

**Connection:**

The reason that an list with 1 or 0 elements doesn't show any bad symptoms is because when we filter out the element, it will either return no elements as it is filtered out, or return the same element. And since there isn't and order to those outputs, we wouldn't see any bad symptoms. But once we start adding more elements in the list, we notice how the bug outputs the correct output in reverse once there is an order.
