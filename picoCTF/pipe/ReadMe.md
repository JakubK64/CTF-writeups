# Pipe

### Description
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/pipe/task.png)

### Solution

When we try to connect to this server using "nc" we automatically get a lot of text, so we need to search rof out flag in the same lane where we write "nc" command. To search in text we are of course using "grep"
```unix
nc 2018shell.picoctf.com 48696 | grep {*}
```
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/pipe/solution.png)

#### *Flag: picoCTF{almost_like_mario_f617d1d7}*
