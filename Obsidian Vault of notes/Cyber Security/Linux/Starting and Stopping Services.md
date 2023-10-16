We may have services which we want to start on launch, or just start it in general.
The first service we will be looking at is the **"Apache"** service.

---
**APACHE**:
	This lets us easily create and host web servers.
	It can let us host files and other stuff which we might want to access or might want another person to access.
	To start it run the command **sudo service apache2 start**
	Your server is up. 
	**Note:
		You might need to install the apache server before it works
		You won't get any confirmation message
		To know if it working type your IP Address in the address bar of your browser**
	To stop it run the command **sudo service apache2 stop**

---
You can also use Python to host stuff instead of apache.
Like this, **python3 -m http.server 80**
That means you want to run the http module on port 80.
After running the command, any file that is in the directory you are currently in will be hosted.

---
Now, imagine you want a particular service to start with the booting up of your system
For that we use the **"systemctl enable {servicename}"** command and to stop it , just use your brain, it's obvious.