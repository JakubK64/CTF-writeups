# Learn gdb

### Decription
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/Basics/learn_gdb/task.png)

### Solution

We can see that we have here program called "run". When we run it we can see, that it decrypt flag from somewhere and save it in global
variable called "flag_buf", but of course doesn't print it.
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/Basics/learn_gdb/solution1.png)

What we need to do is run gdb (GNU debugger, debugger from GNU project).
We run it using:
```unix
gdb run  // here "run" is name of program we want to debug
```

We can run program again. As we can see our flag is stored in variable called "flag_buf". We can for example watch this variable to 
see moment, when it gets something from memory. We can do it using:
```unix
(gdb) watch flag_buf
```

When we have defined watchpoint on this variable we can run program again. It will stop at the beggining of function called "decrypt_flag",
when our variable get some adress. At this moment we can't print anything from this variable. We need to wait for the end of "decrypt_flag"
function. We use "next" which will stop running program when function will end:
```unix
(gdb) next
```

Now, when in "flag_buf" we have decrypted flag we can print it on our screen using:
```unix
printf "%s", (char*) flag_buf    // standrad output syntax from C language
```
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/Basics/learn_gdb/solution2.png)

We get our flag.

#### *Flag: picoCTF{gDb_iS_sUp3r_u53fuL_9fa6c71d}*
