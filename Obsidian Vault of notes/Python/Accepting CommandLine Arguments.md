What I mean by accepting command line args is this.
Let's say the name of the python file is "main.py"
And we made a port scanner. The ip we need to scan will be the argument we will feed the file in the commandline.
Like this , "Python3 main.py 192.168.1.1"
That IP is the argument.
We need to make the python script recognize and collect the argument to input it as the IP variable.
Which is why we need to learn how to accept commandline arguments.

----
First to accept or check for commandline arguments you need to import the "sys" library.
This is what will allow us to access the system library.
![[import sys.png]]

------

Next, we will need to define the variable and specify the index of the value we want the variable to have.
From the example above, leaving out the "Python3" The index of the ip is 1 so we will specify the index to be 1
![[sys.argv.png]]
We use the "sys.argv[<1>]" to tell python that it is the system's 2 argument we will be feeding the variable

---
Now we will tell the program to print the argument to see if it worked
![[accepting cmdline args.png]]

----
Now let's test the program in the commandine
![[cmdline-args example.png]]

---
**TAKING FILE INPUT**
