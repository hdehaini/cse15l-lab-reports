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
                list += parameters[1] + ", ";
                return String.format("List is now: %s", list);
            }
            
        }
        
        return "404 Not Found!";
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

![Image](pictures\labReport2\404errorpage.PNG)

![Image](pictures\labReport2\addincrement.PNG)

![Image](pictures\labReport2\afterincremented.PNG)

![Image](pictures\labReport2\afterincremented3.PNG)

![Image](pictures\labReport2\firstpage.PNG)

![Image](pictures\labReport2\incrementedpic.PNG)

![Image](pictures\labReport2\runnumberserverssh.PNG)

## Part 2

### Reversed Method Debug

Failure-inducing input:
When the length of the array is greater than 1.
```
@Test
  public void hamza_testReversed() {
    int[] input1 = { 0, 1, 2, 3, 4, 5 };
    assertArrayEquals(new int[]{ 5, 4, 3, 2, 1, 0 }, ArrayExamples.reversed(input1));
  }
```

Symptom:
The second half of the array would be symmetrical to the first half, rather than being the reversed of the original array.


Bug:
Changed the original array “arr” rather than the new array “newArray”
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

### Filter Method Debug

Failure-inducing input:
Whenever there is a solution with more than one element

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

Symptom:
It filters the correct elements, but stores them in a reverse order.



Bug:
The code specifically inserted the filtered element at the 0’th index, so I took it out and let the program add the filtered element at the end of the list by default	

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