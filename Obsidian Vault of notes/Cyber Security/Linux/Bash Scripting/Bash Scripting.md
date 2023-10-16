Let me be straight with you.
I know some stuff in programming, I'm sort of like a **JACK OF ALL TRADES**.
But **Bash Scripting** is one that I know very little about.
Well, let's get into it.

---
- **IP SWEEPER**
- 
---
- IP SWEEPER
Technically, this is NMAP, but i want to cure my imposter syndrome so that's what we're doing.

So, firstly :
I want to ping some IP addresses once each and put the results in a text file.
![[Pasted image 20230922101902.png]]

Okay, then I want to only extract the line that has the ip in it , i.e. the line that shows the response (the line with "64 bytes" in it)
![[Pasted image 20230922102124.png]]

Okay, smooth sailing.
Next, I want to extract the fourth element in each of them, that is the ip addresses.
![[Pasted image 20230922102249.png]]

Alright, next I want to remove the colon at the end of the ip so that I can have only the ip address.
![[Pasted image 20230922102358.png]]

Ooookay, we see that it works.
Time for the semi difficult part.
Putting it all in a script that will check for each ip in a specified range automatically.

---
For that we will have to open up a new bash script in mousepad and start the fun part.
I will call the script "ipsweeper"
![[Pasted image 20230922102918.png]]
So we have the file, time to start the scripting.
- First declare that it is a bash script with the line "#!/bin/bash"
- Then we create a "for loop" that will run the command we used above, except this time we won't cat out anything, we will just ping it directly.
- But to go through the whole set, we will need to leave a variable in the ip and add "1" to the variable anytime the for loop repeats itself 

---
- **ALSO, I PUT IN "int i" INSTEAD OF JUST "i" ITSELF**

---
![[Pasted image 20230922105539.png]]
The for loop will count from 1 to 254, meaning it will run 254 times.
Lets do this in relatable terms. I take it you know a bit of programming
The "`seq 1 254`"  is the range.
And for every instance of the loop it will run the code below (`ping -c 1 10.0.0.$i | grep "64" | cut -d " " -f 4 | tr -d ":"`)
And it will replace the last digit of the ip with the value of the variable "**i**"

---
**Let's improve the code.**
Let's make the "10.0.0" and argument so that the user won't have to change to code anytime they have to change the first part of the ip.
![[Pasted image 20230922110502.png]]

---
Now, if the user does not specify any ip then the program will not function well.
![[Pasted image 20230922111150.png]]

So, we need to add an "if statement", if the user add an ip, we run, if not we tell them they need to add an ip.
![[Pasted image 20230922112932.png]]

![[Pasted image 20230922113304.png]]
**I amended my grep**
