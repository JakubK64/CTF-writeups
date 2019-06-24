# Forensics Warmup 2

### Description
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/Forensics/Forensics_Warmup_2/task.png)

### Solution
I don't really understand this task, because I can open this file from the beggining and read the flag. So what I think is a problem in 
this task is find another file extension to open this file.
When we download it we can see that it is simple .png file, but when we check details, we'll see that it isn't .png. We can do it using:
```unix
binwalk flag.png
```
or
```unix
file flag.png
```
Now we can see that it is .jpeg file. We need to change file extension using:
```unix
mv flag.png flag.jpeg
```
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/Forensics/Forensics_Warmup_2/Solution1.png)

And we can read the flag:
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/Forensics/Forensics_Warmup_2/flag.png)

#### *Flag: picoCTF{extensions_are_a_lie}*
