# CSE15L Lab Report 4
## Challenge Tasks

During Week 7's lab, we raced to see who could download a file and edit code thru the terminal fastest. After downloading the required repository, we had to perform these steps in as little time as possible:

- Log in to your ieng6 account on the remote server
- Clone the fork of the lab7 repository from your Github account
- Run the junit tests to show they fail
- Edit the code within the terminal to fix the error
- Run the tests again to prove they passed and the error is gone
- Commit and push the changed code to your Github account

Each step will be broken down in detail below:

## Step 1: Logging in to ieng6:


- To enhance the speed at which the task can be completed, ssh keys can be used to bypass having to enter the password to your ieng6 account.
- To do this, first open a terminal and type `ssh-keygen`. Keep pressing `<enter>` until the message "The key's randomart image is: "
- Once the key's been generated, log into ieng6 (you will have to enter a password)
- Run the command `mkdir .ssh`, then log out of your ieng6 account.
- Within the ssh directory, copy the public ssh key to a file called `authorized_keys`. 
- A couple lines above the "randomart image" line, there will be a line that reads "Your public key has been saved in `/path`". Copy the path.
- From your local device, NOT YOUR ineg6 account, run the command `scp <path to your SSH key> cs15lwi23___@ieng6.ucsd.edu:~/ .ssh/authorized_keys`
- You'll have to enter your password once more, but this is the last time. 
- Try to log in again. You shouldn't be prompted with the password step like you have been before.

![Image](https://i.imgur.com/KAQcJXI.png)




## Cloning the fork and bypassing github password authentication:

- When I was attempting the task, I kept getting a message after entering my Github username & password when attempting to commit or push along the lines of "Github no longer supports password authentication"
- To solve this, you'll have to repeat a similar set of steps as shown above. 
- Instead of copying a key to `authorized_keys` on your `ieng6` account, you'll be saving it to Github instead.
- Once again, in terminal, run `ssh-keygen` and keep pressing Enter until the randomart image shows up.
- To display the SSH public key, run the command `cat <path of ssh key.pub file>`
- Copy the output of the `cat` command, then go to your Github account settings.
- Scroll down, click on **"Access"** and then **"SSH and GPG keys"**.
- Click **"New SSH key"**, add a title, make sure the type is an authentication key, then paste the output from the `cat` command into the key field, then confirm to add the key.
- Now, log in to `ieng6` and run the command `ssh-keyscan -t rsa github.com >> ~/.ssh/known_hosts`. Then run `ssh -T git@github.com`. The displayed message should be something like "Hi <user>! You've successfully authenticated but Github doesn't provide shell access".
- Once all that is done, **make sure to clone the lab7 repository by selecting SSH, not https.**
![Image](https://i.imgur.com/LSrqjq9.png)
Once this is copmplete, you are ready to begin the actual task.

## Cloning your fork of the repository from Github:

- At the end of the previous step, you downloaded the **ssh** version of the lab7 repository. 
- To clone, open terminal, log in to ieng6 (no password required!) and run the command `git clone <ssh link pictured above, in this case git@github.com:username/lab7.git`
- A successfully cloned repository is pictured below:
![Image](https://i.imgur.com/XwnBqzL.png)


## Running the initial test with junit:
- To run the junit tests on the file `ListExamples.java` within the lab7 repository, run these commands:
- Change the working directory to lab7 by typing `cd lab7`, then `ls` to see the files. `TestListExamples.java` is the file to test.
- For mac, enter `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` followed by `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples`. If entered properly, you should see that one test failed. 
![Image](https://i.imgur.com/RS4W5DL.png)

## Editing the code to fix the error:
- To edit the code within `ListExamples.java` without using VScode, we can use the `nano` command to manually edit the code. Enter the command `nano ListExamples.java`, but make sure you are already in the `lab7` directory. You should see this screen:
![Image](https://i.imgur.com/CP2NE7r.png)
- To navigate the file, you can use the arrow keys to move through the text. To locate the error, I pressed `<down>` 42 times to reach the line where the error was. In this case, the error was that in the code block
```
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
       index1  += 1;
```
`index1` was being incremented instead of `index2`. To fix this, press `<right>` 13 times, delete the `1` and replace it with `2` so the code block instead reads:
```
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
       index2  += 1;
```
Once this is changed, press `ctrl O` to save then `enter` then `ctrl X` to exit.

## Re-running the tests to ensure they pass:

- After using `nano` to edit the code within `ListExamples.java`, stay in the `lab7` directory and re-run the same junit tests as above. They should now pass. 
- To access the test commands more easily, press `<up>` until you reach the `javac` command, then the `java` command. For me, it was six presses of `<up>` to access each. Because the code now works properly, you should see this:

![Image](https://i.imgur.com/6g3hovR.png)

## Committing and pushing the changes to ListExamples.java to your Github Account:
- Even though the tests now pass, the file in your Github account now must be updated. 
- To do so, first type `git add ListExamples.java` followed by `git commit -m "<any message to signify the file is updated>"`
- Now, you should see a message containing the `<any message to signify the file is updated>` as well as `1 file changed, 1 insertion(+), 1 deletion(-)`. 
- You have now successfully committed the changes to the file!

![Image](https://i.imgur.com/RQ9TDRC.png)

Now, you've successfully completed the task designated during Week 7's Lab!
