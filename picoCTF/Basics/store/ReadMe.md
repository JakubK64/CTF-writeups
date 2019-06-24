# Store

### Description
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/store/task.png)

### Solution

We have simple program and its source code i C language. We can buy our flag here, but we don't have enough money.

When we analize source code we can see, that there is only one place when we can affect to "account_balance" (variable which contains our
account ballance). When we try to buy "not real flag" we can input how many flag we want to buy. Program only checks if this number is 
grater than 0 and when it is -> total_cost = 1000*number_flags (simple multiplication to generate total cost of this transaction).

Next thing what program do is check if total_cost is less or equal with account_balance - for obvious reason. If it is program will do:
account_balance = account_balance - total_cost - again, for obvious reason. But if we make total_cost as negative number our account
balance will grow up instead of decrease.
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/store/sourcecode.png)

So we have validation if integer is greater than 0 and we need to input negative number. To do it we need to use integer overflow technique.
It base on input number, that is over max range of standard integer type. So if we input any number greater than 2147483648 our account
balance will grow up. To buy flag we need at least 100.000 so we need to input at least 2147483547 (we have 1.100 when program starts)
to get enough money on our account.
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/store/solution2.png)

When we have enough money on our account we can just buy a flag from store.
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/store/solution2.png)

#### *Flag: picoCTF{numb3r3_4a3nt_s4f3_6bd13a8c}*

#### Bonus:

When we open **program file** in notepad you can easy read a flag without even running it.
![alt text](https://github.com/JakubK64/CTF-writeups/blob/master/picoCTF/store/notes_flag.png)
