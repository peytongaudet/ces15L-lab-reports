# CSE 15L Lab Report Vim
## Peyton Gaudet (A17573280)

**Part 1: Week 6 Task**

The task I chose to do was the first one where we were asked to change the name of the start parameter and its uses to base. Below are the list of keystrokes along with screenshots I used to complete the task:

* `/start`

I used the `/<string>` command to find the use of start in the getFiles() method. Luckily, this method was at the top and there were no previous uses of start elsewhere so it jumped to the start instance that I needed to change right away.

![Image](vim.1.1.png)

* `ce`

I used this command to switch into insert mode and delete the word start. The commnad `ce` means to make a change all the way to the end of the current word your cursor is at.

![Image](vim.1.2.png)

* `base <esc>`

While in insert mode and at the correct spot where I needed to change the name of start to base, I simply typed in `base` and pressed `<esc>` to enter back into normal mode.

![Image](vim.1.3.png)

* `n.` x2

Using the command `n` repeated the last search that I made. So, it found the next instance of start, which needed to be changed. The `.` command repeats the previous commands which were explained in steps 2 and 3. There was one more instance of start that needed to get changed to base so we used the same sequence of commands to acheive. Now, our goal is complete.

Using `n`:
![Image](vim.1.4.1.png)
Using `.`:
![Image](vim.1.4.2.png)

* `:wq`

Since our goal is now completed, we can use the command `:wq` to save our work and quit vim. In total, we used 20 keystrokes to complete our task!

![Image](vim.1.5.png)



**Part 2: Running Remotely**

1. Using VSCode:

The time it took me to make the edit in VSCode, then scp the file to the remote server and run it there to confirm it worked was 1 minute and 59 seconds. I had the scp command in my command history already so making sure that I copied into the right directory was not an issue. However, making sure that I was in the right directory to run the test script was an issue that cost me some time. In general, I feel I was pretty efficient using this method.

2. Using Vim:

The time it took me to make the edit for the task I chose in Vim, then exit Vim and run the test script was 30 seconds. I think that already being logged into the server saved me some time. However, let's say logging in takes me 15 seconds max, I was still able to save 1:15 seconds. I didn't run into any issues and it was much easier to make sure I was in the right directory before using the test script.


3. Conclusion:

Honestly, before doing this lab I thought I was deadset on avoiding Vim. However, after doing this short experiment, I can see the many benefits of using it and I'm going to try to use it more often. Although the Vim shortcuts don't seem very intutive to begin with, they are easy to learn and extremely efficient. 
A factor that might lead me away from Vim would be my familiarity with the program. If it was a program that I wasn't too familiar with, it would be difficult for me to navigate around using an unfamiliar tool like Vim. However, as I got more comfortable with details of the program, I could see myself switching to Vim to navigate and make edits in the program. Also, as stated in class, if the program is on a remote server, it seems much more efficient to use Vim to make edits.
