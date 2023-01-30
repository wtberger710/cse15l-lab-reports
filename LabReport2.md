# Lab Report 2: Servers & Bugs
## Part 1: Creating a Web Server



This is the code I used to create the web server (based on the server used in Week 2's lab:

![image](https://i.imgur.com/sv9NLbO.jpg)

These are the two messages I tested:

![image](https://i.imgur.com/7v8BLsh.jpg)


![image](https://i.imgur.com/vrEoID7.jpg)


The method called for both the first and second screenshot is the `handleRequest` method pictured above:

![image](https://i.imgur.com/rT7D6eu.jpg)

- However, this `if` statement pictured above is what takes the user's input of "Hello" and "How are you" and translates it into the web server.
- The relevant arguments are the changes made to `parameters`, as well as `return String.format("%s\n", result);` which formats each user input (such as "Hello" and "How are You") and prints each on a separate line.
- Initially, before any user input is added to the server, `String result` has no value. Typing `/add-message?s=Hello` gives `result` a value, so that changes depending on user input. The same applies for `/add-message?s=How are you`

 ## Part 2: Bugs

- One of the bugs in lab 3 was that for the method `reverseInPlace`, which was intended to take an array, say `{1, 2, 3}` for example, and reverse the positions of the corresponding outer and inner values, so it should yield `{3, 2, 1}`.  
The method `reverseInPlace` is shown below:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i+=1) {
        int temp = arr[i];
        arr[i] = arr[arr.length-i-1];
        arr[arr.length-i-1] = temp;
    }
}
```
A failure inducing input for `reverseInPlace` is shown below:
```
public void testReverseInPlace2() {
        int[] input1 = {1, 2};
        ArrayExamples.reverseInPlace(input1);`
        assertArrayEquals(new int[]{ 2, 1 }, ArrayExamples.reversed(input1);
}
```
![image](https://i.imgur.com/TPIR2vF.jpg)
The reason `2` is expected here but not `1` even though a "reversed" array for an input of `{1, 2}` is because the initial code block for `reverseInPlace` runs twice as many times as it should. 

An input that doesn't indluce failure is shown below:
```
public void testReverseInPlace2() {
        int[] input1 = { 1 };
        ArrayExamples.reverseInPlace(input1);`
        assertArrayEquals(new int[]{ 1 }, ArrayExamples.reversed(input1);
}
```
![image](https://i.imgur.com/Tbqe5lu.jpg)

This input doesn't cause failure because reversing an array of only one value will always yield the same array, so the test will always pass for this case.

For reference, here is the method `reverseInPlace` again, before debugging:
```
    for(int i = 0; i < arr.length; i+=1) {
        int temp = arr[i];
        arr[i] = arr[arr.length-i-1];
        arr[arr.length-i-1] = temp;
    }
}
```

Now, this is the debugged method `reverseInPlace` running properly:
```
    for(int i = 0; i < arr.length/2; i+=1) {
        int temp = arr[i];
        arr[i] = arr[arr.length-i-1];
        arr[arr.length-i-1] = temp;
    }
}
```
The reason the only fix necessary was changing the runtime of the for loop to `arr.length/2` instead of it being `arr.length` is because what was happening is that the method would run, swap the intended values, then swap them back because the loop would run too many times. A full loop would swap the values, then swap them back to their original positions as if nothing happened at all. To fix this, halving the runtime ensures that the swap is only made the necessary number of times. 

## Part 3: Something you learned

One thing I learned during week 3's lab was how to make my own web server that could be modified at will. I learned about the required imports and methods needed to properly run the server, as well as what each character in the search bar meant, as without every character, the command wouldn't run as intended. 
