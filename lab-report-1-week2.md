# Lab Report 1: Week 2
This lab is a tutorial about how to log into a course-specific account on ieng6.
## Step 1: Installing Visual Studio Code
Firstly, We need to install the [Visual Studio Code](https://code.visualstudio.com/) in our computer.
![VSCode Download](https://user-images.githubusercontent.com/129908756/230742292-476df3eb-cacb-4268-a302-c059142035d2.jpg)

After installing the VSCode and open the VSCode, We will see the Welcome Page in VSCode(get started).

<img width="1349" alt="VSCode Start Page" src="https://user-images.githubusercontent.com/129908756/230742413-1127138c-5bef-4d9a-a794-d0185afded1e.png">
It is fine if the welcome page looks a little bit differently due to the differences of systems and settings.

## Step 2: Remotely Connecting
In this section, we will learn about how to login the remote server by our CSE15L Account.

Firstly, We need to know our CSE15L Student account. We can Look up our course-specific account for CSE15L at [CSE 15L Account](https://sdacs.ucsd.edu/~icc/index.php). Here is also a tutorial about how to reset our CSE15L Password provided by the teaching staff in CSE15L:[Reset CSE15L Account Password](https://drive.google.com/file/d/17IDZn8Qq7Q0RkYMxdiIR0o6HJ3B5YqSW/view)

(Extra Step Needed for Windows):
We need install [git for Windows](https://gitforwindows.org/) for Windows. When we finish the installation, we need to set our default terminal to use the newly-installed `git bash` in Visual Studio Code. [Tutorial Provided by the blog](https://stackoverflow.com/questions/42606837/how-do-i-use-bash-on-windows-from-the-visual-studio-code-integrated-terminal/50527994#50527994)

Now, we are ready to use `ssh` to log in the remote server. To use `ssh`, open a terminal in VSCode. (Ctrl or Command + `, or use the Terminal → New Terminal menu option). Your command will look like this, but with the `zz` replaced by the letters in your course-specific account.

```
$ ssh cs15lsp23zz@ieng6.ucsd.edu
```
