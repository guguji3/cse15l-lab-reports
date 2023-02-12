# Lab Report 2 - Servers and Bugs

## part 1

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
   String content = "";

   public String handleRequest(URI url) {
       if (url.getPath().contains("/add-message")) {
           String message = url.getQuery().split("=")[1];
           content += message + '\n';
           return content;
       } else if (content.equals("")) {
           return "Missing info! Input a message";
       } else {
           return "404 Not Found!";
       }
   }
}

class StringServer {
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

![image](https://user-images.githubusercontent.com/86742001/218337147-15a064f4-58e0-473d-a008-2f81c86bdc6f.png)

* **Which methods in your code are called?**: handleRequest and main
* **What are the relevant arguments to those methods, and the values of any relevant fields of the class?**: The argument to the handleRequest method is the URL, "http://localhost:4002/add-message?s=Hello", and the argument to the main method is the port number, [4002]. The values of fields are port number, [4002], the content, "Hello", and the output, "Hello\n". 
* **How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.**: The URL changes from "http://localhost:4002" to "http://localhost:4002/add-message?s=Hello", the content changes from "" to "Hello", and the output changes from empty to "Hello\n".

![image](https://user-images.githubusercontent.com/86742001/218337288-c4043f22-1b36-4f64-a856-eac144f54cb4.png)

* **Which methods in your code are called?**: handleRequest and main
* **What are the relevant arguments to those methods, and the values of any relevant fields of the class?**: The argument to the handleRequest method is the URL, "http://localhost:4002/add-message?s=How%are%you", and the argument to the main method is the port number, [4002]. The values of fields are port number, [4002], the content, "How are you", and the output, "Hello\nHow are you\n". 
* **How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.**: The URL changes from "http://localhost:4002/add-message?s=Hello" to "http://localhost:4002/add-message?s=How%are%you", the content changes from "Hello" to "How are you", and the output changes from "Hello\n" to "Hello\nHow are you\n".

## part 2

* **failure-inducing input**
```
@Test
 public void testReverseInPlace() {
   int[] input1 = {1,2};
   ArrayExamples.reverseInPlace(input1);
   assertArrayEquals(new int[]{2,1}, input1);
 }
 ```
 * **success-inducing input**
```
@Test
 public void testReverseInPlace() {
   int[] input1 = {0};
   ArrayExamples.reverseInPlace(input1);
   assertArrayEquals(new int[]{0}, input1);
 }
 ```
 * **sympton**
 
 ![image](https://user-images.githubusercontent.com/86742001/218340211-5d103303-b04f-40a9-a9dd-c05b82e05e07.png)

* **before-and-after code**
```
// Changes the input array to be in reversed order
 static void reverseInPlace(int[] arr) {
   for(int i = 0; i < arr.length; i += 1) {
     arr[i] = arr[arr.length - i - 1];
   }
 }
```
```
// Changes the input array to be in reversed order
 static void reverseInPlace(int[] arr) {
    int length = arr.length;
    for (int i = 0; i < length / 2; i++) {
        int temp = arr[i];
        arr[i] = arr[length - i - 1];
        arr[length - i - 1] = temp;
    }
}
```
The issue for the before code is that the issue with the loop, it swaps each element with the same element from the other end of the array, resulting in the array being unchanged. I use the variable temp to store the value of the element being swapped, and it updates both elements in a single iteration. By only looping over half of the array, each element is swapped only once, which results in the array being reversed in place.

## part 3

I have learned how to build and run a server on a remote computer, including setting up the necessary software and configurations, and executing commands to start and stop the server, and how to create a web server.  I have also learned how to write tests that detect symptoms and failure-inducing input, which can be helpful to catch bugs early in the development process and ensure that the code works as intended. It can save more time
