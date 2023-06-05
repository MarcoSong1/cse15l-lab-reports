# Lab Report 5 - Putting it All Together

## Part 1 Debugging Scenario

Ed Question:

### What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?

MacOS / VSCode / VSCode Integrated Terminal

### Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.

I want to create a script `JavaCommand.sh` to compile and run a Java program: `sample.java`. However, after I running the script on the terminal, it seems that I could not successfully run the java file. I do not know what's going on as my code looks good for me.

<img width="1045" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/d98f11ea-6488-43ed-a240-3fc247f40459">
<img width="893" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/e10644f7-9eff-4877-8de4-7dbd5e428765">
<img width="683" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/a3654ef0-5b0e-43e2-9db3-61896ea5ffbd">

### Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.

After creating the script and `sample.java` file, I first set the directory to `CSE15L` by opening the integrated terminal from `JavaCommand.sh`. After typing `chmod +x JavaCommand.sh` on terminal(gives execute permission) and `./JavaCommand.sh`, I got the weird behavior that I could not complie and run the java program I created.

### TA's Response

Hi, I think your script code looks almost fine. The issue should be the path you are dealing with. Note that inside `CSE15L` folder, you still have a sub folder `java_sample` inside `CSE15L`, which stores your java file. When you are calling `JavaCommand.sh` on terminal, you are in `CSE15L` path. I suggest you be more careful about the path inside your script in the example you provided. Do you observe the path issue? Is the path consistent in your script? There should be multiple ways to fix the weird behavior that your code does.

### Student fixed the bug

After receiving TA's feedback, I realized that the buggy part was in my script about the path. The `sample.java` is inside `java_sample` folder, but the script is inside `CSE15L` folder. When I running the script on the terminal, the content of script file did not handle the path issue. I should set the directory to the path where `sample.java` located.

<img width="1019" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/6e98b1f7-90b9-46d9-b20a-b3072e084c26">
<img width="602" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/d7353f71-a53b-4bc0-a96a-a4ba0afda5a6">

Another way to fix the bug is to remove `java_sample` folder and to move all files to `CSE15L` folder since `java_sample` folder is unnecessary here. In this case, we can keep original code without set directory in the script by `cd`. Rather, we should change from `java_file="/Users/songkunhao/Desktop/CSE15L/java_sample/sample.java"` to `java_file="/Users/songkunhao/Desktop/CSE15L/sample.java"` since we delete `java_sample` folder. Note that the path I will run `JavaCommand.sh` will be `CSE15L` on the terminal in this case.

<img width="808" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/4e22595a-1193-470e-b9a7-e835c1a1e34b">
<img width="1021" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/07bc7fbb-557b-4353-90fd-1a7754e59135">
<img width="658" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/0e102385-c6b7-431a-8ab0-0043de1be446">

### Set-up to fix the bug

#### The file & directory structure needed

In method 1 to fix the bug, we need to set directory to the place where `sample.java` located by using `cd`. Orginally, I wrote the script code intended to we run the java program. Inside `java_sample` folder, I created `sample.java` file as my test file to test my script.

In method 2 to fix the bug, I only have one folder `CSE15L`. I removed `java_sample` folder, and put 
my script and `sample.java` inside `CSE15L` folder. Then I changed `java_file="/Users/songkunhao/Desktop/CSE15L/sample.java"`

#### The contents of each file before fixing the bug

Before fixing the bug, the content of the script was the screenshot above. The content of `sample.java` was just printing `"Hello, world!"`.

#### The full command line (or lines) you ran to trigger the bug

open integrated terminal on VSCode, which sets the path to `CSE15L` from `JavaCommand.sh`.

Set execute permission on the script by typing `chmod +x JavaCommand.sh` on the terminal.

Run the script by typing `./JavaCommand.sh` on the terminal

Then we triggered the bug

#### A description of what to edit to fix the bug

This section was discussed in student's response to TA's feedback. To summarize, we have at least two ways to fix the bug, either adding changing path command `cd` in `JavaCommand.sh` or removing `java_sample` folder and change `java_file`'s path located at `CSE15L`.

## Part 2 – Reflection

I had no idea about what shell script is. Before learning about this, I was exhausted about typing some repeated commands in the terminal. Learning from this class, I know that we could actually store these commands in a shell script. In this case, we do not need to run so many tedious commands over and over again, but rather just running the script. It saves me a lot of time when coding, especailly we can store common commands that we often use in the script. Also, Vim is very powerful as we do not need mouse anymore to change and edit code. This can be extremely time-saving when we are very familar with commands on Vim. I learned a lot of techniques and knowldege about coding and computer from this class!✌🏻











