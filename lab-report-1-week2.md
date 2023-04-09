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

Now, we are ready to use `ssh` to log in the remote server. To use `ssh`, open a terminal in VSCode. (Ctrl or Command + `, or use the Terminal → New Terminal menu option). 

Our command will look like this, but with the `zz` replaced by the letters in our course-specific account.

```
$ ssh cs15lsp23zz@ieng6.ucsd.edu
```
After typing my password, my terminal looks like this:

<img width="621" alt="Log in ssh" src="https://user-images.githubusercontent.com/129908756/230743311-c21aadff-3675-46f3-99e2-b72d7e9820ca.png">

`Observation`: It is normal that the information on terminals varies. The reason why I got this information is that it is not my first time log in CSE15L remote server. When I logged in the remote server for the first time, I received some warnning information: `Are you sure you want to continue connecting (yes/no/[fingerprint])?` After typing yes, I successfully logged in the remote server: `Hello cs15lsp23zz, you are currently logged into ieng6-203.ucsd.edu`. However, I never receive this warning information when I log in the remote server afterwards. Hence, the information shown on the terminals might be different from people to people. It contains some personal information and different warnings, which might be due to the differences of systems, times of log-ins, etc. 

As long as our terminal shows information about Cluster Status, it is a good indication that we successfully logged in the remotre server.
<img width="319" alt="Success Login" src="https://user-images.githubusercontent.com/129908756/230743645-58adaafd-985e-4afd-ad71-f5f6c0918457.png">

Now, We have successfully logged in the remote server of CSE15L!

## Step 3: Trying Some Commands
For the remaining parts, let's try some commands on the terminal. 

Command List:
* `cd ~`

* `cd`

* `ls -lat`

* `ls -a`

* `ls <directory> where <directory> is /home/linux/ieng6/cs15lsp23/cs15lsp23abc`, where the `abc` is one of the other group members’ username

* `cp /home/linux/ieng6/cs15lsp23/public/hello.txt ~/`

* `cat /home/linux/ieng6/cs15lsp23/public/hello.txt`

Information shown on the terminal:

<img width="690" alt="Command" src="https://user-images.githubusercontent.com/129908756/230751947-3cba92db-f6da-4387-a738-2c4faf8fc789.png">





