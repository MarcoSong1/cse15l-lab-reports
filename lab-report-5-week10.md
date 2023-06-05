# Lab Report 5 - Putting it All Together

## Part 1 Debugging Scenario

Ed Question:

### What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?

MacOS / VSCode / VSCode Integrated Terminal

### Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.

My script code want to find a file in a speficed path. My file and script are in the same path. 
It should find the file with my script code. However, after I running the script on the terminal, 
it shows that " File not found at path" in the given path. I am not sure why I got this werid behavior. Since I could successfully run the
script code, but the file could not be found even though script and file.txt are in the same path.

<img width="872" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/770b734e-d7d7-4953-b128-833259dc8699">
<img width="639" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/1fe4f741-3112-4144-9413-d49b92a048bf">

### Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.

After creating the script and file.txt file, I first set the directory to `sh_script` by typing `cd sh_script` on terminal. After typing `./check_file.sh` on terminal, I got the weird behavior.

### TA's Response

Hi, I think your script code looks fine. The issue should be the path you are dealing with. Note that inside `CSE15L` folder, you still have
a sub folder 'sh_script` inside `CSE15L`. When you are calling `check_file.sh` on terminal, you are inside `sh_script` path. I suggest you
be more careful about the `file_path` inside your script in the example you provided. Do you observe the path issue? There should be multiple ways to fix the weird behavior that your code does.

### Student fixed the bug

After receiving TA's feedback, I realized that the buggy part




