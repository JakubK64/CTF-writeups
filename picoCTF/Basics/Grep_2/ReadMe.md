# Grep 2

### Description 
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/Basics/Grep_2/task.png)

### Solution

Another time we need to use "grep" to find flag in directory. Of course we start with check what contains indicate directory using:
```unix
ls -l
```

As we can see we have 10 directories inside which contain many text files each. We need to use "-r" option in grep to search our pattern in all files including all subdirectories:
```unix
grep -r {*}
```

![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/Grep_2/solution.png)

#### *Flag: picoCTF{grep_r_and_you_will_find_24c9llab}*
