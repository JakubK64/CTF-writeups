# Absolutely relative

### Description
![alt text]()

### Solution

We can find 3 files in this directory -> program "absolutely-relative", source code of this program "absolutely-relative.c" and 
text file "flag.txt" which contain our flag. When we try to execute "absolutely-relative" we get information, that we don't have permissions to view the flag
![alt text]()

We need to analize source code to find way to get permission to "flag.txt" file. We can see here:
1. Our flag from "flag.txt" is reading from file and saving into variable calls "flag"
2. Some permission is reading from "permission.txt" file and saving into "permission" variable
3. Here is strncmp (string compare) function, that compare "permission", "yes" and "yes_len" (both define an the top op source code)

As we can see we need to let program read "yes" from permission.txt file and then 3 section will print us flag. But we must remember that
we don't have permission to create any file in this directory. How it works ?

Program read "flag.txt" file from full path, but it is also reading "permission.txt" file from our current directory. All we need to do
is create file calls "permission.txt" in directory where we can do it and execute program from there (for example from our home directory)

So we go back to our home directory, where we have permission to create new file
```unix
cd
```

next we create permission.txt file which contain "yes" inside using"
```unix
echo "yes" > permission.txt
```

and at the end we execute program 
```unix
/problems/absolutely-relative_0_d4f0f1c47f503378c4bb81981a80a9b6/absolutely-relative
```

#### *Flag: picoCTF{3v3r1ng_1$_r3l3t1v3_a97be50e}*
