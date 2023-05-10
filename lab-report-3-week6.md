# Lab Report 3 - Researching Commands
In this report, I will explore 4 useful comand-line options for `find`. `find` command is a useful tool for us to search for some files or directories based on different criteria for our needs, such as name, file, type, etc.

## Option 1: Find files by type(`-type` option)

After I typed `find command-line options` on google, I scrolled down a little bit. Then, I found this useful and concise descriptions about some command-line options for `find`. This source explores 10 ways to use find command.

Source: https://www.redhat.com/sysadmin/linux-find-command

Example 1:

```
find ./technical -type d
```
Output:
```
./technical
./technical/government
./technical/government/About_LSC
./technical/government/Env_Prot_Agen
./technical/government/Alcohol_Problems
./technical/government/Gen_Account_Office
./technical/government/Post_Rate_Comm
./technical/government/Media
./technical/plos
./technical/biomed
./technical/911report
```
The `-type` option can help us to search for files or directories based on the types. In this case, it is usefuly to use `-type d` option if we want to search for directories inside `./technical`.

Example 2:

```
find ./technical -type f
```
Output:
```
./technical/plos/journal.pbio.0030127.txt
./technical/plos/pmed.0010058.txt
./technical/plos/pmed.0010070.txt
./technical/plos/pmed.0010064.txt
./technical/plos/pmed.0020158.txt
./technical/plos/journal.pbio.0020042.txt
./technical/plos/journal.pbio.0020297.txt
./technical/plos/pmed.0020206.txt
./technical/plos/pmed.0020212.txt
./technical/plos/pmed.0020216.txt
./technical/plos/journal.pbio.0030094.txt
./technical/plos/journal.pbio.0020046.txt
./technical/plos/pmed.0020028.txt
...
```
By using `-type f`, it allows us to find all files inside `./technical`, it is helpful if we want to look at the files without their directories.

## Option 2: Find Empty(`-empty` option)

This time, I searched `Find command in Linux` on google. By exploring a little bit, I found this source that is concise and easy to understand for some `find` options. Here, I want to talk about `-empty` option.

Source: https://www.tecmint.com/35-practical-examples-of-linux-find-command/  (No.19,20)

Example 1:

```
find ./technical -type d -empty
```

Output:
```
Nothing was shown on the terminal
```
Learning from Option 1, we used `-type d` to find all directories. By combining it with `-type d -empty`, we will find all empty directories under `./technical` path. This one can be useful to detect if there is any empty directory under `./technical` path. In this case, there is no empty directories under `./technical` path.

Example 2:

```
find ./technical -type f  -empty
```

Output:
```
Nothing was shown on the terminal
```
Learning from Option 1, we used `-type f` to find all files under `./technical` path. By combining it with `-type f -empty`, we will find all empty files under `./technical` path. This one can be useful to detect if there is any empty file under `./technical` path. In this case, there is no empty files under `./technical` path.

## Now, let's use ChatGPT to help us find the rest two options as our sources.










