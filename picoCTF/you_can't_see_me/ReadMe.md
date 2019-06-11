# You can't see me

### Description
![alt text]()

### Solution

We have directory with hidden file inside. To see hidden files we need to add "-a" to ls command
```unix
ls -la
```

We can see that we have one file which name is ".". This is special sytuation, because we can't use "cat" to files named like this
("." is also current directory in linux so we can't use "cat" command to directory, "." is also special character in unix system).
To show text from this file we need to use:
```unix
cat .*
```

This command allow us to cat every file which name starts with "." (in this directory only file with flag)
![alt text]()

#### *Flag: picoCTF{j0hn_c3na_paparapaaaaaaa_paparapaaaaaa_22f627d9}*
