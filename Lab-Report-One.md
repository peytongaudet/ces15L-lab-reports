# CSE 15L Lab Report 1
## Peyton Gaudet (A17573280)

---
**Part 1: Installing VSCode** 

To install VSCode follow this [link](https://code.visualstudio.com/Download) to the VSCode download website. 
Once there, click on the download button for the opertating system that you are using and follow the steps to install VSCode from their website.

![Image](LR(11).png)



**Part 2: Remotely Connecting**

To remotely connect:
1. Look up your course-specific account for CSE15L [here](https://sdacs.ucsd.edu/~icc/index.php) and follow the instructions provided.

2. Open a terminal in VSCode using Ctrl or Command + `. Then type in the command below: 
```
$ ssh cs15lfa22zz@ieng6.ucsd.edu
```
("zz" is replaced with your specific account id)

3. Since, it is your first time logging in, you will likely get a prompt about your RSA key. Answer yes to this.

4. Enter your password that you made from Part 1. (Passwords are typed with no feedback in the terminal, but it will be logging your keystrokes for your password. Press enter when done.) 
If you see the message below in your terminal after enterting your password, you have successfully remotely connected!

```
Hello cs15lfa22zz, you are currently logged into ieng6-203.ucsd.edu
```

![Image](LR1(2).png)

**Part 3: Trying Some Commands**
Below are some commands that were used in the screenshot provided and some explanations as to what they are doing:

* “cat” was used to print the contents of hello.txt file
* “ls” was used many times to list the files and folders in the current directory 
* “pwd” was used to show what the current directory is. (this command was not shown being used in the screenshot)
* “cd” was used to change the directory that is actively being used (cd ~ brings us back to the home directory)
* “mkdir” was used to make a new directory called peyton

![Image](LR1(3).png)

**Part 4: Moving Files with "scp"**

The steps needed to use the "scp" command are as follows:

1. Make sure the files that need to be copied over are saved on your local computer.
2. Use the command
```
scp <path> cs15lfa22zz@ieng6.ucsd.edu:~/
```
to copy over the file to the server computer. You will be prompted for your password.

3. To check if the file was successfully copied over, remotely login to the computer you sent the file to and use the "ls" command to locate the file in its home directory. 

![Image](LR1(4).png)

**Part 5: Setting an SSH Key**

Running the command below creates a pair of files known as public and private keys:
```
$ ssh-keygen
```
After running this, you will be prompted to enter a preferably shorter passphrase that will help speed up certain processes that require a password. Before you are able to use your new, shortened passphrase, you must send the *public* (not the private) key to the user account on the server computer. *Make sure to take note of where you saved the public key to, because you will need to include it while copying it over to the server computer as we learned previously.* Use the "scp" command to copy the public key file from your computer over to the server and then you will be able to use your shortened passphrase next time you login! 

![Image](LR1(5).png)

**Part 6: Optimizing Remote Running**

Below was my attempt to reduce the amount of keystrokes necessary to complete the task of running the "WhereAmI" java program remotely. I shortened my passphrase a little more before starting this and ran the program while being logged in on my local computer. I was able to do this by using quotation marks around my command which directly runs the command, which in this case was the program, on the remote server, and then exits as shown below:
```
$ ssh cs15lfa22lg@ieng6.ucsd.edu "java WhereAmI"
```
Hopefully, I'll be able to look back on this at the end of the quarter and think that this was too many keystrokes, but I'm happy with its efficiency!

![Image](LR1(6).png)