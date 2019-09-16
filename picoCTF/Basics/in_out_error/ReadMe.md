# in out error

### Decription
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/Basics/in_out_error/task.png)

### Solution

We have 2 files in this directory: program calls "in-out-error" and "flag.txt" file.
When we try to run it we don't get anything special
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/Basics/in_out_error/solution1.png)

One example way to get flag from this program is to redirect stderr (standard error output) to any text file (we don't have permission to
create any file in this directory so we need to do it for example in our home directory).
```unix
./in-out-error 2>> ~/tmp.txt    // 2>> will append text from stderr, we can also use here 2> to rewrite file (if it isn't empty)
```

When we do it correctly we get long message, 
something like letter starting with "Thank you for asking so nicely!".
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/Basics/in_out_error/solution2.png)

Last thing we need to do is open out text file, when we can find our flag wrote multiple times.
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/Basics/in_out_error/solution3.png)

#### *Flag: picoCTF{p1p1ng_1S_4_7h1ng_b6f5a788}*

