# Environ

### Description
![alt txt](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/environ/task.png)

### Solution

We only now that flag is in one of environment variables. We can try our luck check for example variable calls FLAG using:
```unix
echo $FLAG
```

but it doesn't make sense to try find flag this way. The best way is to use "printenv" command to print on screen all environment variables.
There is many of them on this serwer so we need to use grep to find our flag:
```unix
printenv | grep {*}
```
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/environ/solution.png)

#### *Flag: picoCTF{eNv1r0nM3nT_v4r14Bl3_fL4g_3758492}*
