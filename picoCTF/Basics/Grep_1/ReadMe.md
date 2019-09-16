# Grep 1

### Description

![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/Basics/Grep_1/task.png)

### Solution

First of all when we connect to directory with our task is find if is there any file using:
```unix
ls -l
```

Now we see that it is file name "file" in this directory.
If we try to "cat" this file we can see, that it contain many random characters.
We need to search "file" looking for flag pattern:
```unix
grep {*} file
```

![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/Grep_1/Solution.png)

There is only our flag matching to this pattern

#### *Flag: picoCTF{grep_and_you_will_find_42783683}*
