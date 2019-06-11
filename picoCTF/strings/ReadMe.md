# Strings

### Description
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/strings/task.png)

### Solution

First of all we need to check what files we can find in this directory using:
```unix
ls -l
```

We can see only one file - "strings". This is binary file, we need to get text from this file and find our flag.
We use "strings" command to get text from binary file and then search on result using grep:
```unix
strings strings | grep {*}
```
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/strings/Solution.png)

#### *Flag: picoCTF{sTrIngS_sAVeS_Time_2fbe2166}*
