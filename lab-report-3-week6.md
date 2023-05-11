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
By using `-type f`, it allows us to find all files inside `./technical`, it is helpful if we want to look at the files without their directories. This one can be helpful when sometimes we only want to focus on certain types of file/directories, which can save us lots of time by this filtering property. Also, we can combine this option with other options. Please see options below to check it out!

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
Learning from Option 1, we used `-type f` to find all files under `./technical` path. By combining it with `-type f -empty`, we will find all empty files under `./technical` path. This one can be useful to detect if there is any empty file under `./technical` path. In this case, there is no empty files under `./technical` path. This option can be helpful when we want to identify some empty files or directories, especially when we want to clean up these empty files/directories or investigate whether certain data has been missed.

# Now, let's use ChatGPT as our sources to help us find the rest two options.

Prompt I asked ChatGPT:
![30621683749439_ pic](https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/f6ea2bef-55aa-419b-a59d-d0bd0675da54)

ChatGPT gave me several options. Here, I want to discuss the options `-iname` and `-newermt`

## Option 3: Case-Insensitive Name Searching(`-iname` option)
The answer ChatGPT gave me:
![30631683750646_ pic_hd](https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/4f493fae-baf2-4250-b5fb-7fa31e52f7a8)
![30641683750658_ pic](https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/29b80588-d4b5-437a-827b-1ac42e1ccee1)

According to ChatGPT, "the `-iname` option is similar to -name but is case-insensitive, allowing searching for files and directories based on their name using case-insensitive shell pattern matching."

Example 1:

```
find ./technical -iname '*.TXT'
```

Output:
```
./technical/plos/pmed.0010071.txt
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
./technical/plos/journal.pbio.0020052.txt
./technical/plos/pmed.0020148.txt
./technical/plos/pmed.0020160.txt
...
```

In this case, `find ./technical -iname '*.TXT'` finds all files with the .txt extension under `./technical` path even though we typed '*.TXT' since `-iname` is case-insensitive. It can be helpful to find some files we are interested in if we do not care about cases.

Example 2:

```
find ./technical -iname 'report*'
```

Output:
```
./technical/government/About_LSC/reporting_system.txt
./technical/government/Post_Rate_Comm/ReportToCongress2002WEB.txt
```

By learning from ChatGPT, in this case, we found all files and directories with names starting with "report" or "Report" within the ./technical directory and its subdirectories. This can be more powerful than `-name` if we do not care about cases of our searches as it is more effective. Unlike, `-name`, this can be especially helpful when sometimes we are inconsistent about case choices, which can prevent from misssing some files.

## Option 4: Searching Newer Than Specified Date(`-newermt` option)
The answer ChatGPT gave me:
![30671683751441_ pic_hd](https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/3906f521-c846-4314-b02a-5934e6703d7f)
![30661683751388_ pic](https://github.com/MarcoSong1/cse15l-lab-reports/assets/129908756/48c005df-c9c9-4910-a158-3fb034d8db6c)

According to ChatGPT, "the -newermt option allows searching for files or directories that are newer than a specified date or time."

Example 1:

```
find ./technical -type f -newermt '2023-05-07'
```

Output:
```
Nothing was shown on the terminal
```

In this case, `find ./technical -type f -newermt '2023-05-07'` searches for all files under `./technical` directory and its subdirectories that have modification time newer than '2023-05-07'. Since this date is brand new, there is no modification in recent days in files under
`./technical`

Example 2:

```
find ./technical -type d -newermt '2022-04-01'
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

In this example, `find ./technical -type d -newermt '2022-04-01'` searches for all directories within the `./technical` directory and its subdirectories that have a modification time newer than date `2022-04-01`

This option can be useful for us to look for modified files or directories in certain periods to review the changes of files or directories, which can help to track our works.














