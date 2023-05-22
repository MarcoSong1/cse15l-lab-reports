# Lab Report 4 - Timing Command Line Tasks

## Step 1 Setup: Delete existing forks

Delete the existing forks of the repository on your account in order to have a clean state. This can be done by going to `Settings` on Github and go to `Danger Zone` section and delete the repository.

On VSCode Terminal:

We could use the following commands:

<img width="485" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/68dc81e8-8a7b-4886-b207-d783e91df2a2">

Keys I used for deleting:

`rm -rf lab7 <enter>`

## Step 2 Setup: Fork the repository

Go the the repository that we want to fork.

<img width="1299" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/5b0f7e87-acb6-4f9f-aee1-15e98f76e5c3">

## Step 3 Setup: Start Timing

we have finished the setup. Let's do our tasks!

## Step 4: Log into ieng6

We need use `ssh` to log into ieng6 account.
<img width="948" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/d7d4ab4c-666e-4e16-be02-3ea1927f8ea1">

Note: I did not enter my passcode. This is because I finished 'Generating SSH Keys for ieng6' part in week 7 lab, which could save me a lot of time.

Keys I used:

`ssh cs15lsp23qp@ieng6.ucsd.edu <enter>`, where `qp` is my account name.

## Step 5: Clone the fork of the repository from Github account

Go to the repository:

Since I have already generated SSH Keys for GitHub, I could use `SSH` instead of just using `HTTPS`.

![image](https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/bb9d96e6-8cbc-47dc-8d17-d197cac75aed)

Go to VSCode Terminal to clone the repository:

<img width="878" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/e6ae4298-ae6e-42bf-9165-b4861a0229cd">

Keys I used:

`git clone git@github.com:MarcoSong1/lab7.git <enter>`

Now, we have finished the clone task.

## Step 6: Run the tests

The comands I used on VSCode:

<img width="754" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/5263bf67-9992-48a7-a7bc-828bf3138a4f">

Keys I used:

`cd lab7 <enter>`, which changes the directory to lab7.

`ls <enter>` to see the content of lab7 directory.

`bash test.sh <enter>` to run the tests.

Reason I used these commands:

I think using `bash test.sh <enter>` is fast. If we typed `vim test.sh` on terminal. We will see the following:

<img width="973" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/0007c667-0fe9-4f96-b8e2-2facb27de9eb">
  
Instead of typing long commands `javac ...` and `java ...`, which complie files and run the tests. We could store the commands in `test.sh` and run `bash test.sh <enter>` to avoind the annoying typing and save a lot of time!

Using `:q! <enter>` to exit the vim.

## Step 7: Edit the code file to fix the failing test

Using `vim` to edit the code:

<img width="976" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/45b63912-3ba9-4894-b433-9682d294262f">

Key I used:

`Vim ListExamples.java <enter>`

Key I used to find the position of buggy code:

`/index1 <enter>`, and then typed `n` 9 times.

<img width="935" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/3cd1b18c-8299-4bc7-84d6-58f4bf893fd3">

Key I used to fix the buggy code:

typeed `l` 5 times to go the target posistion:

<img width="948" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/c67d54fe-c66f-49da-a213-020694bad32d">

typed `r` and `2` to change `index1` to `index2`

<img width="1017" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/3cf78370-db02-4644-a600-37caa49e8849">

typed `esc` to normal mode

typed `:wq! <enter>` to exit and save.

## Step 8: Run the tests and Pass


Keys I used:

`<up><up><up> <enter>` to access 'bash test.sh` again.

<img width="591" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/2f99620e-7e0c-4e98-ab6a-2d3ec3de9f43">

## Step 9: Commit and push the resulting change Github account

Keys I used:

`git add . <enter>` -- add files

`git commit -m "Fix bug" <enter>` -- commit changes
  
`git push <enter>` -- push changes to GitHub
  
<img width="800" alt="image" src="https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/bfc3bd70-3333-48ba-b583-d1719a739529">







  
  













