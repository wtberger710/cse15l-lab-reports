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

One of the bugs in lab 3 was





```
