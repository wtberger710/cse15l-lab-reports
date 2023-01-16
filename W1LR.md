# CSE15L Week 1 Lab Report
## Remote Access

In this post, you'll learn how to:

- Download Visual Studio Code
- Remotely connect to a remote server by logging into an ieng6 account
- Run commands on the remote server

## How To Download Visual Studio Code:


- Open up a web browser and search "visual studio code download" or click this link: [Download VS Code](https://code.visualstudio.com)
- Follow instructions on the website to properly download and open VS Code, but be sure to download the right version for your specific computer (i.e. Windows/Mac/Linux)
- Once Visual Studio Code has finished downloading, be sure to open it and make sure it's running properly. An example of a properly downloaded and running Visual Studio Code should look like this:

![Image](https://i.imgur.com/XXSSS3X.png)

## Accessing The Remote Server:

- To access the remote server using an `ieng6.ucsd.edu` account, the steps are slightly different depending on whether you use Mac or Windows
- For Mac, it's fairly straightforward. Just open the `Terminal` application and type `ssh cs15lwi23xy@ieng6.ucsd.edu` NOTE: Each user has a course-specific account, the "xy" is just an example. 
- To find your specific username, go to [https://sdacs.ucsd.edu/~icc/index.php]() and log in to view your course-specific CSE15L username
- For Windows users, there are a couple extra steps. First, download `Git` by clicking this link: https://gitforwindows.org/
- Next, check out this link to set Git up properly: https://stackoverflow.com/a/50527994
- To use `ssh`, open a terminal in VScode by pressing Ctrl/Command + or use the `Terminal > New Terminal Menu` option. 
- The command itself is the same as for a Mac. Enter `ssh cs15lwi23xy@ieng6.ucsd.edu`. If it is your first time connecting, you'll be prompted to confirm whether you want to connect or not. This is common when connecting for the first time. After confirming, you will be prompted to enter your password
- Once you've entered your password, you will successfully be logged in to a computer in the CSE building's basement, and any commands you enter from your own device will run on that specific CSE basement computer. The image below shows the response once your password has been entered

 ![Image](https://i.imgur.com/F2RFa9g.png)


## Commands On The Remote Server

- There are some basic commands you can run on the remote server. Examples are:
- `cd ~` also known as chdir (change directory) is a command used to change the current working directory
- `ls` this is the list command, which will return the folders and/or files within the current directory. More specific commands are `ls -lat` and `ls -a` which both are variations of the "list" command
- `pwd`this command writes out the full path name of your curretn directory from its root, all separated by a `/`
- `mkdir` allows users to create or make new directories/folders from the terminal
- `cp` allows users to make a copy of a file
![Image](https://i.imgur.com/LNLp7Ti.png)
The above image shows examples of three different commands, `ls -lat`, `ls -a`, and `pwd`. `ls -lat` returns a list of all the folders and/or files in the current directory, `ls -a` lists the contents of the present working directory, and `pwd` returns the full path name of your current working directory. 
